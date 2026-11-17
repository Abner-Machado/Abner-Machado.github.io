---
title: "Most of my agent bill was re-reading the same prompt"
date: 2026-11-17
category: "Agent cost and quota"
description: "I measured thirty days of real coding-agent sessions. Output was 14 percent of the cost. The cached prefix was 84. That changes what is worth optimizing."
---

For months I optimized the wrong thing. I trimmed replies, I asked for shorter answers,
I told the agent to stop explaining itself. Reasonable instincts. All of them aimed at
output.

Then I instrumented thirty days of my own sessions. Output was 14 percent of what I
spent. The cached prefix, the same instructions re-read at the top of every single
turn, was 84 percent. New input, the thing I actually typed, was about 1.

## Why the prefix is the bill

A turn is not an isolated question. Every turn ships the whole conversation again:
system prompt, project instructions, memory files, tool schemas, the transcript so far.
The provider caches that so it is cheap per token. Cheap per token is not cheap. You
pay it again on turn 2, and on turn 40, and the thing keeps growing.

So the cost curve has a shape nobody warns you about. A long session with short replies
is expensive. A short session with long replies is not.

That inverts the usual advice. Short answers are good manners. They are not a cost
strategy.

## What the volume numbers hide

Here is the part that convinced me. Counted by raw token volume, output was 0.5 percent
of my traffic. Counted by what it costs, it was 14 percent. A cached token and an output
token are both called a token and they are nothing alike.

| Where it goes | Share of cost |
|---|---|
| Cached prefix, re-read each turn | 84% |
| Output | 14% |
| New input I typed | 1% |

I wrote [turnburn](https://github.com/Abner-Machado/turnburn) to do this counting, because
reading the raw transcript and summing tokens gives you the volume answer, which is the
wrong answer. It weights each class by cost instead: a re-read cached token at a fraction,
an output token at a multiple. Then it tells you which turn burned the most.

The first time I ran it on myself the top turn was not a build or a long refactor. It was
a turn where the agent re-read a file it had just written.

## The three things that actually moved

### Delegate context, not writing

This was my big mistake. I used to hand off heavy
writing to a cheaper model, which saves at most a slice of that 14 percent and fails in
its own ways. What saves real money is keeping context out of the main thread. A
sub-agent that sweeps forty files and comes back with one paragraph never puts those
forty files into the prefix you pay for on every later turn. Searching, mapping,
locating: that is what to hand off. Architecture and decisions stay where the context
already is.

### Read before you edit

I measured 221 reads against 460 edits. Half a read per edit.
Editing a file you have not read produces a failed edit, a retry, and a longer
transcript, and that transcript is the prefix. The cheap-looking shortcut is the
expensive one.

### Watch what you put at the top

Instructions, memory, tool definitions. Everything up
there gets billed on every turn for the rest of the session. A paragraph that is wrong
costs you once in output and forever in prefix. I now treat my instruction file as the
hottest code path in the system, because that is what it is.

## The part I still have not solved

I can see the burn after the fact. I cannot see it live, which means I still discover a
bad session at the end instead of at minute three. A budget that trips while the prefix
is still small would be worth more than every trimmed reply I have ever written.

If you are optimizing an agent and you have not measured where the cost sits, measure
first. Mine was not where I was looking, and I had been looking confidently for months.
