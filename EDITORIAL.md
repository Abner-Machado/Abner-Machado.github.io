# Editorial contract

What this blog is, how a post gets written, and what never ships. Read this before
drafting anything.

## The one-line version

Take the problem seriously, never take the absurdity of this work too seriously, find
the root cause, and publish the number you measured.

## Voice

First person. Respect first: the reader is a working engineer, not an audience for a
roast. No sarcasm aimed at people, no dunking on a library, a vendor or whoever wrote
the code being debugged. Argue with the decision, never with the person who made it.

Dry humor is seasoning. It shows up when the situation is genuinely absurd and then it
gets out of the way. There is no joke quota. A post with zero jokes and one good
measurement beats a post with six jokes and no number.

Plain words. Short sentence next to a long one. Say "I was wrong about this" when that
is what happened, and say it once, without ceremony.

Personality shows up as concrete detail, not as a bit. The third coffee at two in the
morning belongs in a post only if that is actually when the thing broke.

## What this blog is about

Four subjects. If a draft does not fit one of them, it does not go up.

### Agent cost and quota
 Where the money and the rate limit actually go. Cached prefix
against output, what delegation really saves, how to measure a session instead of
guessing at it.

### Small machine, real work
 Running models and pipelines on a laptop with no GPU.
Memory bandwidth as the ceiling, quantization, what fits and what does not, measured on
hardware most posts pretend does not exist.

### When the agent gets it wrong
 Guardrails, poisoned skill files, retrieval that went
stale, failures frozen into something reproducible. The failure path, not the happy one.

### Build it instead of renting it
 Open source first, with the license, the last commit
date and the monthly price in the local currency. What a subscription actually buys and
what it quietly costs.

## The technical bar

Every post:

- Explains the mechanism, not only the steps. If the reader cannot predict what happens
  when they change one input, the post failed.
- Shows real code or a real command when there is one.
- Separates what was measured from what is believed. Write "I measured" or "I think",
  never let the reader guess which one it was.
- Says why this solution beats the alternatives that were tried.
- Names performance and security consequences where they exist.

Never fabricate terminal output, a benchmark, a test result or an incident. If a number
is not on disk somewhere, it does not go in the post. Never present untested code as
production ready.

## What we do not do

No fixed narrative formula. A structure repeated post after post reads as generated,
and that is the exact impression this blog cannot afford.

No SEO apparatus. One honest title and one honest description. No keyword lists, no
alternative headline variants, no internal linking quota.

No roundups, no "top 10", no reaction pieces about somebody else's announcement.

No stock programmer jokes. If the line already exists on the internet, cut it.

No invented seniority. Competence gets demonstrated by reasoning and numbers, or it does
not get claimed.

## Rhythm

One post every two weeks, written when there is something measured to report. Eight real
posts in a year beat thirty thin ones and a six month gap. A visible gap on a blog reads
worse than a short archive.

## Look

Aged photographic plate, industrial workshop, hand tools, old technical manuals,
monochrome and warm. Editorial layout, generous margins, type doing the work.

No futuristic AI illustration, no neon gradient, no stock photography of people pointing
at monitors. Images earn their place by showing something, or they do not appear.

Imagery that is illustrative is never captioned as documentary, and no generated face is
ever presented as a photograph of a real person.

## Before publishing

1. Does every number in this post exist in a file somewhere?
2. Is there a sentence that could have been written by someone who did not do the work?
3. Does it fit one of the four subjects?
4. Would an engineer who disagrees with it still finish it?
5. Run the text through the anti pattern lint and get a clean exit.
