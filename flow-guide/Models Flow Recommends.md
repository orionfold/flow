---
title: Models Flow Recommends
tags: [flow, models, agency]
catalogueVersion: 2
models:
  - id: mlx-community/Qwen2.5-7B-Instruct-4bit
    displayName: Qwen 2.5 7B Instruct
    weightBytes: 4295887610
    agencyBaseline: flow-agency-v1
    note: The most reliable tool-user in this list. Ask for it if your Mac has room.
  - id: mlx-community/Llama-3.1-8B-Instruct-4bit
    displayName: Llama 3.1 8B Instruct
    weightBytes: 4534808112
    agencyBaseline: flow-agency-v1
    note: Strong at following instructions exactly, which is what an edit needs.
  - id: mlx-community/Mistral-7B-Instruct-v0.3-4bit
    displayName: Mistral 7B Instruct
    weightBytes: 4080220722
    agencyBaseline: none
    note: Fast for its size, and steady on long documents.
  - id: mlx-community/Phi-3.5-mini-instruct-4bit
    displayName: Phi 3.5 Mini Instruct
    weightBytes: 2152172448
    agencyBaseline: none
    note: Small, and unusually good at producing structured answers.
  - id: mlx-community/Llama-3.2-3B-Instruct-4bit
    displayName: Llama 3.2 3B Instruct
    weightBytes: 1824807894
    agencyBaseline: none
    note: Lightweight for general writing and comfortable on almost any Apple silicon Mac.
  - id: mlx-community/Qwen2.5-3B-Instruct-4bit
    displayName: Qwen 2.5 3B Instruct
    weightBytes: 1747849050
    agencyBaseline: none
    note: The smallest here. Capable on short work, and quick.
---

# Models Flow Recommends

Flow's editor, reader, vault, search, tables and charts work with no model at all. **Agency does not.** Summarising a document, proposing an edit, checking a draft against your own guidance: all of it needs a model somewhere.

There are three ways to give Flow one, and none of them is better than the others in general. Which is better depends on your Mac.

## The three ways

**A model on this Mac.** You download it once and it runs locally, forever, for nothing. Your documents never leave the machine. The catch is memory: a model's weights have to fit alongside everything else your Mac is doing, and a model that is too large will not run at all.

**An account you already pay for — not yet.** Using a Claude or ChatGPT subscription through the tool it provides is a route Flow is building, and it is not in this release. Until it lands, the two routes on either side of this paragraph are what Flow can use.

**A metered account.** An API key with a provider, billed by usage. Predictable and fast, and the only route that costs money per run.

You can have all three. Flow picks between them per task, and always tells you which it used. See [[Cost of This Quarter]] for what that looks like once there is something to show.

## What "fits" means

Flow reads your Mac's actual memory rather than looking your model up in a table. A MacBook Pro 14" ships in several memory configurations, so the name on the box does not answer the question; the number does.

A model's weights are not the whole cost. The context you give it, the helper's own buffers and the rest of macOS all need room too, which is why Flow will not propose a model whose weights alone take a large share of your memory. It also checks free disk space, since a download that leaves your volume full is one you pay for twice.

For its first general Agency engine, Flow considers only entries explicitly marked as meeting its current Agency quality baseline. It then recommends the smallest of those that fits this Mac, minimizing the first download without pretending size is a quality score. Smaller specialist models remain available to choose yourself.

If none of the baseline-qualified models fits your Mac, **Flow says so and suggests an account instead**, rather than proposing a download that cannot succeed.

## The list

The models above are all MLX conversions, which is the format Apple silicon runs fastest. They are all *instruct-tuned*, and that matters far more than size: at identical parameter counts, an instruction-tuned model follows a structured request reliably where its base version essentially cannot. The catalogue separately marks which entries Flow is prepared to recommend as a general Agency engine; the rest can still be useful specialist choices.

Sizes are the real download, measured from the model's own file listing. Nothing here is estimated.

For repeatable Flow Runtime measurements on named Mac hardware, see [[Curated Model Comparisons]]. Those comparisons are unranked evidence, not another recommendation list.

| Model | Download | General Agency | Good at |
| --- | ---: | --- | --- |
| Qwen 2.5 7B Instruct | 4.3 GB | Meets Flow's current baseline | Following a tool or schema precisely |
| Llama 3.1 8B Instruct | 4.5 GB | Meets Flow's current baseline | Instruction-following on longer work |
| Mistral 7B Instruct | 4.1 GB | Specialist choice | Speed at its size |
| Phi 3.5 Mini Instruct | 2.2 GB | Specialist choice | Structured output from a small model |
| Llama 3.2 3B Instruct | 1.8 GB | Specialist choice | Lightweight general writing |
| Qwen 2.5 3B Instruct | 1.7 GB | Specialist choice | Short work, quickly |

## Flow keeps this list current

This document updates itself along with the rest of this folder, so the list reflects what is worth running today rather than what was worth running when you installed Flow.

**Your edits are safe.** If you change this document, Flow does not overwrite it. It offers you the update and lets you decide, the same as any other document here.

## Downloading is not the last step

A model that runs is not yet a model Flow knows how to use well. Once one is on your Mac, **measure it**: Flow times it against a fixed piece of work and records the result. That measurement is what lets Flow choose the right model for each task instead of guessing from size.

Flow will propose the measurement itself once there is something to measure.
