---
title: Local Runtime Evaluation
tags: [evaluation, models, technical]
---

# Runtime Evaluation — Local Models

> **Fictional example.** This document shows how a team can record an evaluation and its decision. The people, dates and results are invented; they are not Flow benchmark results. For measured model evidence, see [[Model Evidence]].

**Example owner:** platform · **Example date:** October 14, 2026 · **Status:** decided

We spent three weeks answering one question: can we do our document work on models that run on our own machines, without asking every writer to install and babysit a separate piece of infrastructure? The answer is yes, and this note records what we measured and what we decided.

## Why this came up

The security review in August turned on a single sentence in the questionnaire: *where does the document text go?* Every answer that involved a third-party endpoint added a review cycle. Every answer that kept text on the machine did not. That is the whole business case — the engineering question was only whether local models were good enough to do the work.

## What we compared

![A workstation running models locally](assets/quiet-desk.jpeg)

*Local models run on the machine already on the desk — no separate service to install or babysit.*

| Route | Where it runs | Setup a writer does | Cost per run |
|:------|:--------------|:--------------------|-------------:|
| Built-in runtime | This Mac | Choose and download a compatible model | $0.00 |
| Ollama, served in place | This Mac | Install Ollama, pull models | $0.00 |
| LM Studio, served in place | This Mac | Install LM Studio, pull models | $0.00 |
| Hosted API | Provider | Add a provider API key | Provider token charges |

In this example, the team used the same model and document set across the three local routes, and judged all three adequate for its tasks. Setup effort decided the choice. A real evaluation should retain the exact model versions, hardware, prompts and scored outputs before drawing that conclusion.

## The finding that decided it

**The example team chose the route with the least setup work.** We watched six people onboard. The two who were handed a runtime to install both stalled — one on a download that looked like a hang, one on a model that accepted an add and then failed every request afterward. The four using the built-in runtime began work after their model downloads completed.

The second finding was about trust rather than speed: people wanted to know which model answered, and they wanted it attached to the change rather than sitting in a log somewhere. A run that could not say what produced it got treated as suspect regardless of whether the output was good.

## What we standardized on

- **Built-in runtime as the default** for everyone, with the disk allowance set to 20 GB. Writers download a compatible model through Flow; no separate runtime app is required.
- **Serve in place** for the two engineers who already keep models in Ollama. Their gigabytes are not downloaded a second time and removing a model from our list never touches their files.
- **Hosted stays permitted but off by default.** Turning it on is a deliberate act, and each run records its route.

## Open items

- Evaluate diagram review separately, using the actual images and a supported vision route. A text-only comparison does not establish image capability.
- We have not yet measured what happens to throughput when two people on the same machine run at once. Nobody does this today; it will matter when the shared review box arrives.
