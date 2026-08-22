---
title: Runtime Evaluation — Local Models
tags: [evaluation, models, technical]
---

# Runtime Evaluation — Local Models

**Owner:** platform · **Date:** October 14, 2026 · **Status:** decided

We spent three weeks answering one question: can we do our document work
on models that run on our own machines, without asking every writer to
install and babysit a separate piece of infrastructure? The answer is
yes, and this note records what we measured and what we decided.

## Why this came up

The security review in August turned on a single sentence in the
questionnaire: *where does the document text go?* Every answer that
involved a third-party endpoint added a review cycle. Every answer that
kept text on the machine did not. That is the whole business case — the
engineering question was only whether local models were good enough to
do the work.

## What we compared

![A workstation running models locally](assets/quiet-desk.jpeg)

*Local models run on the machine already on the desk — no separate service to install or babysit.*

| Route | Where it runs | Setup a writer does | Cost per run |
|:------|:--------------|:--------------------|-------------:|
| Built-in runtime | This Mac | None — it ships with the app | $0.00 |
| Ollama, served in place | This Mac | Install Ollama, pull models | $0.00 |
| LM Studio, served in place | This Mac | Install LM Studio, pull models | $0.00 |
| Hosted, prepaid | Provider | Sign in to an existing plan | Covered |
| Hosted, postpaid | Provider | Paste an API key | Per token |

The three local routes were indistinguishable in output quality on our
own documents. They differ entirely in what we have to ask a writer to
do before they can work, which is why the built-in runtime won.

## The finding that decided it

**Setup cost, not model quality, is what stops adoption.** We watched
six people onboard. The two who were handed a runtime to install both
stalled — one on a download that looked like a hang, one on a model
that accepted an add and then failed every request afterward. The four
who used the built-in runtime were working in under a minute.

The second finding was about trust rather than speed: people wanted to
know which model answered, and they wanted it attached to the change
rather than sitting in a log somewhere. A run that could not say what
produced it got treated as suspect regardless of whether the output was
good.

## What we standardized on

- **Built-in runtime as the default** for everyone, with the disk
  allowance set to 20 GB. Nobody installs anything.
- **Serve in place** for the two engineers who already keep models in
  Ollama. Their gigabytes are not downloaded a second time and removing
  a model from our list never touches their files.
- **Hosted stays permitted but off by default.** Turning it on is a
  deliberate act, and the domain switch makes that visible.

## Open items

- The vision-capable models we want for the diagram review are partly
  landed — the Qwen-VL and Gemma vision lines load, and one model family
  we asked about does not exist upstream yet. Revisit in November.
- We have not yet measured what happens to throughput when two people
  on the same machine run at once. Nobody does this today; it will
  matter when the shared review box arrives.
