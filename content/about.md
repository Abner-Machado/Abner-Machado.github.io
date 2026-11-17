---
title: "About"
description: "Abner Machado, agent engineer in Sao Paulo. Open source tooling for agents that fail with a trace."
---

I am Abner Machado. I work on the layer around coding agents: orchestration across
several models, guardrails, retrieval, and the boring plumbing that decides whether a
run costs you five cents or five dollars.

Most of my day is spent on one laptop. An i3 with 24 GB of RAM, integrated graphics,
no GPU. That constraint shaped everything I believe about this field. When a tool only
works with a rented A100 behind it, I do not get to use it, so I measure first and
build the small version myself.

## What I publish

All of it is MIT or Apache, all of it runs offline, and none of it needs a signup.

- [allied-code](https://github.com/Abner-Machado/allied-code). A pre-execution guard for
  coding agents that decides from recorded incidents instead of a static blocklist.
- [TraceDNA](https://github.com/Abner-Machado/TraceDNA). Freezes a flaky failure into a
  plain text capsule, then knocks out one method at a time to tell you which method the
  failure actually needs.
- [turnburn](https://github.com/Abner-Machado/turnburn). Reads a session transcript and
  shows where the quota burned, weighted by what each token really costs instead of by
  volume.
- [agent-layer](https://github.com/Abner-Machado/agent-layer). Small tools for the agent
  layer: catches a poisoned skill file, gives a retrieval base an expiry date. Zero
  dependencies, no network.
- [consilience](https://github.com/Abner-Machado/consilience). Finds the links your notes
  are missing. Local, semantic, no cloud.
- [potatollm](https://github.com/Abner-Machado/potatollm). Measures whether a given model
  will actually run on a weak CPU-only machine, instead of guessing from parameter count.

## How I work

Open source first, and I mean the order, not the vibe. Mature project, then something
self-hostable, then an open standard, then build it myself. A paid service is the last
option and it has to come with the monthly number attached.

Smallest change that solves the problem. I do not rewrite what works to match my own
taste, and I would rather ship three similar lines than an abstraction nobody asked
for yet.

A green test proves the author's imagination, not the code. So I run the error path by
hand: missing argument, corrupted file, exit code without a pipe. That is where the
six real bugs were last time I counted.

## Elsewhere

[GitHub](https://github.com/Abner-Machado) ·
[X](https://x.com/Fezrix) ·
[YouTube](https://www.youtube.com/@Fezrix)

Sao Paulo, Brazil.
