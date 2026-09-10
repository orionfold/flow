---
title: Models Flow Recommends
tags: [flow, models, agency]
catalogueVersion: 3
researched: 2026-09-09
models:
  - id: mlx-community/gemma-3-text-4b-it-4bit
    displayName: Gemma 3 4B IT (language-model-only export) 4-bit
    weightBytes: 2600191231
    agencyBaseline: flow-agency-v2
    class: both
    tiers: [16, 24, 32-36, 48-64, 96-128, 256+]
    revision: 4f665a4c50ecfe4ecdc34056ab52fe3e3c4abf9e
    servedWindow: 8192
    kvBytesPerToken: 139264
    workingSetBytes: 4589538256
    evidence: measured
    evidenceSource: signed receipt 0012b886019826a5c9f3950a6fef938819c40983dbdc155bb37208d816ffccc4
    tokensPerSecond: 91.4
    timeToFirstTokenSeconds: 1.6
    baselineComposed: 8
    baselineProbeCount: 8
    dayBaselineComposed: 8
    dayBaselineProbeCount: 8
    nightBaselineComposed: 0
    nightBaselineProbeCount: 3
    measuredTier: 32-36
    qualitySource: LMArena lmarena-ai/leaderboard-dataset text_style_control/latest, published 2026-09-02
    note: Composes 8 of 8 on Flow's agency baseline in one turn; 91 tokens a second, 1.6 s to the first token.
  - id: mlx-community/Mistral-7B-Instruct-v0.2-4bit
    displayName: Mistral 7B Instruct v0.2 4-bit
    weightBytes: 4264704510
    agencyBaseline: flow-agency-v2
    class: both
    tiers: [16, 24, 32-36, 48-64, 96-128, 256+]
    revision: 64481e3a4a7bb0990c45c991958f8d6c00c1e785
    servedWindow: 8192
    kvBytesPerToken: 131072
    workingSetBytes: 6400528536
    evidence: measured
    evidenceSource: signed receipt 0012b886019826a5c9f3950a6fef938819c40983dbdc155bb37208d816ffccc4
    tokensPerSecond: 57.0
    timeToFirstTokenSeconds: 2.8
    baselineComposed: 8
    baselineProbeCount: 8
    dayBaselineComposed: 8
    dayBaselineProbeCount: 8
    nightBaselineComposed: 0
    nightBaselineProbeCount: 3
    measuredTier: 32-36
    qualitySource: LMArena lmarena-ai/leaderboard-dataset text_style_control/latest, published 2026-09-02
    note: Composes 8 of 8 on Flow's agency baseline in one turn; 57 tokens a second, 2.8 s to the first token.
  - id: mlx-community/Llama-3.1-8B-Instruct-4bit
    displayName: Llama 3.1 8B Instruct 4-bit
    weightBytes: 4534824337
    agencyBaseline: flow-agency-v2
    class: day
    tiers: [24, 32-36, 48-64, 96-128, 256+]
    revision: 90215b22ec18e72f623dde2ea7af4097025160e2
    servedWindow: 8192
    kvBytesPerToken: 131072
    workingSetBytes: 6508630456
    evidence: measured
    evidenceSource: signed receipt 0012b886019826a5c9f3950a6fef938819c40983dbdc155bb37208d816ffccc4
    tokensPerSecond: 54.8
    timeToFirstTokenSeconds: 2.8
    baselineComposed: 8
    baselineProbeCount: 8
    dayBaselineComposed: 8
    dayBaselineProbeCount: 8
    nightBaselineComposed: 1
    nightBaselineProbeCount: 3
    measuredTier: 32-36
    qualitySource: LMArena lmarena-ai/leaderboard-dataset text_style_control/latest, published 2026-09-02
    note: Composes 8 of 8 on Flow's agency baseline in one turn; 55 tokens a second, 2.8 s to the first token.
  - id: mlx-community/granite-4.1-8b-4bit
    displayName: Granite 4.1 8B 4-bit
    weightBytes: 5245635681
    agencyBaseline: none
    class: day
    tiers: [24, 32-36, 48-64, 96-128, 256+]
    revision: 08fb1e272f7bd49fa83ce279bbdc496c980380ac
    servedWindow: 8192
    kvBytesPerToken: 163840
    workingSetBytes: 7032197992
    evidence: measured
    evidenceSource: signed receipt b8f52fb8292ad1eb05233b2bb61c6f525bbe348eb245bd35dc29b7a47d482045
    tokensPerSecond: 44.5
    timeToFirstTokenSeconds: 3.5
    nightBaselineComposed: 1
    nightBaselineProbeCount: 3
    measuredTier: 32-36
    qualitySource: LMArena lmarena-ai/leaderboard-dataset text_style_control/latest, published 2026-09-02
    note: Loads and runs on Flow Runtime; the agency baseline has not been run on it; 45 tokens a second, 3.5 s to the first token; below the day speed floor.
  - id: mlx-community/gemma-3n-E4B-it-lm-4bit
    displayName: Gemma 3n E4B IT (language-model-only export) 4-bit
    weightBytes: 3903219922
    agencyBaseline: none
    class: day
    tiers: [24, 32-36, 48-64, 96-128, 256+]
    revision: 00b5ecdc79ba872a9b4cd32f4327e263bab5936c
    servedWindow: 8192
    kvBytesPerToken: 71680
    workingSetBytes: 7222005912
    evidence: measured
    evidenceSource: signed receipt cc8f33b3cadd266c75e05c7e0a189694cda36e0e1bf60d95c5016c1a0112e684
    tokensPerSecond: 61.4
    timeToFirstTokenSeconds: 2.3
    nightBaselineComposed: 0
    nightBaselineProbeCount: 3
    measuredTier: 32-36
    qualitySource: LMArena lmarena-ai/leaderboard-dataset text_style_control/latest, published 2026-09-02
    note: Loads and runs on Flow Runtime; the agency baseline has not been run on it; 61 tokens a second, 2.3 s to the first token.
  - id: mlx-community/gemma-3-text-12b-it-4bit
    displayName: Gemma 3 12B IT (language-model-only export) 4-bit
    weightBytes: 7225400219
    agencyBaseline: none
    class: day
    tiers: [32-36, 48-64, 96-128, 256+]
    revision: 83eda451975103fff6f11e97bf75cd0f1c61af2c
    servedWindow: 8192
    kvBytesPerToken: 393216
    workingSetBytes: 10404763888
    evidence: measured
    evidenceSource: signed receipt cc8f33b3cadd266c75e05c7e0a189694cda36e0e1bf60d95c5016c1a0112e684
    tokensPerSecond: 34.1
    timeToFirstTokenSeconds: 5.1
    baselineComposed: 1
    baselineProbeCount: 8
    dayBaselineComposed: 1
    dayBaselineProbeCount: 8
    nightBaselineComposed: 2
    nightBaselineProbeCount: 3
    measuredTier: 32-36
    qualitySource: LMArena lmarena-ai/leaderboard-dataset text_style_control/latest, published 2026-09-02
    note: Composes 1 of 8 on Flow's agency baseline in one turn, so not yet a pick; 34 tokens a second, 5.1 s to the first token; below the day speed floor.
  - id: mlx-community/gemma-4-26b-a4b-it-4bit
    displayName: Gemma 4 26B A4B IT 4-bit
    weightBytes: 15373588575
    agencyBaseline: flow-agency-v2
    class: night
    tiers: [32-36, 48-64, 96-128, 256+]
    revision: 0d77464eeb233a2da68ebf9d7dc4edaac7db956d
    servedWindow: 8192
    kvBytesPerToken: 245760
    workingSetBytes: 18122403960
    evidence: measured
    evidenceSource: signed receipt b8f52fb8292ad1eb05233b2bb61c6f525bbe348eb245bd35dc29b7a47d482045
    tokensPerSecond: 75.7
    timeToFirstTokenSeconds: 1.8
    baselineComposed: 7
    baselineProbeCount: 8
    nightBaselineComposed: 7
    nightBaselineProbeCount: 8
    measuredTier: 32-36
    qualitySource: LMArena lmarena-ai/leaderboard-dataset text_style_control/latest, published 2026-09-02
    note: Composes 7 of 8 on Flow's agency baseline with its own lookups and keeps Flow's pick: one decline does not displace a pick; 76 tokens a second, 1.8 s to the first token.
  - id: mlx-community/Qwen3.8-27B-4bit
    displayName: Qwen 3.8 27B 4-bit
    weightBytes: 16081490933
    agencyBaseline: flow-agency-v2
    class: night
    tiers: [32-36, 48-64, 96-128, 256+]
    revision: 3e6447f082e89cc7f0bc6e5441afd38dfce760ff
    servedWindow: 8192
    kvBytesPerToken: 262144
    workingSetBytes: 19081589456
    evidence: measured
    evidenceSource: signed receipt b8f52fb8292ad1eb05233b2bb61c6f525bbe348eb245bd35dc29b7a47d482045
    tokensPerSecond: 17.3
    timeToFirstTokenSeconds: 11.1
    baselineComposed: 8
    baselineProbeCount: 8
    nightBaselineComposed: 8
    nightBaselineProbeCount: 8
    measuredTier: 32-36
    qualitySource: LMArena lmarena-ai/leaderboard-dataset text_style_control/latest, published 2026-09-02
    note: Composes 8 of 8 on Flow's agency baseline with its own lookups; 17 tokens a second, 11.1 s to the first token.
---

# Models Flow Recommends

Flow's editor, reader, vault, search, tables and charts work with no model at all. **Agency does not.** Summarising a document, proposing an edit, checking a draft against your own guidance: all of it needs a model somewhere.

There are three ways to give Flow one, and none of them is better than the others in general. Which is better depends on your Mac.

## The three ways

**A model on this Mac.** You download it once and it runs locally, forever, for nothing. Your documents never leave the machine. The catch is memory: a model's working set has to fit alongside everything else your Mac is doing, and a model that is too large will not run at all.

**An account you already pay for: not yet.** Using a Claude or ChatGPT subscription through the tool it provides is a route Flow is building, and it is not in this release. Until it lands, the two routes on either side of this paragraph are what Flow can use.

**A metered account.** An API key with a provider, billed by usage. Predictable and fast, and the only route that costs money per run.

You can have all three. Flow picks between them per task, and always tells you which it used. See [[Cost of This Quarter]] for what that looks like once there is something to show.

## Two models, not one

Flow keeps two picks for a Mac. The **day model** sits beside your work and answers while you are typing, so it is judged on how fast its first word arrives and held to a third of your Mac's memory. The **night model** has the Mac to itself for the Night Shift, so it is judged on accuracy and on how much it can read at once, and may take three fifths of memory. On a small Mac the two are one model; on a large one they are usually different.

## What "fits" means

Flow reads your Mac's actual memory rather than looking your model up in a table. A MacBook Pro 14" ships in several memory configurations, so the name on the box does not answer the question; the number does.

A model's weights are not the whole cost. The context you give it, the helper's own buffers and the rest of macOS all need room too. Flow judges the **working set**, the memory the helper actually holds with the model loaded and a document in front of it, against each class's budget. It also checks free disk space, since a download that leaves your volume full is one you pay for twice.

For either pick, Flow considers only entries marked as meeting its **agency baseline**: a fixed set of tasks run through Flow's own loop on Flow Runtime, which the model must complete every time. It then recommends the smallest such model that fits this Mac, minimizing the first download without pretending size is a quality score. The other rows remain available to choose yourself.

If no baseline-qualified model fits a class on your Mac, **Flow says so and suggests an account for that work instead**, rather than proposing a download that cannot succeed.

## Measured, or projected

Every number in the tables below says how it knows. **Measured** rows were run on a 36 GB MacBook Pro with an Apple M3 Max, through Flow Runtime, with the receipt signed by Orionfold; the numbers are that Mac's, not yours. **Projected** rows have not been run: their working set is computed from the model's own files, and they fill a cell so that no tier of Mac is left without a candidate. A projected row is never a pick.

## The tables, by memory

The models are all MLX conversions, which is the format Apple silicon runs fastest, and all *instruct-tuned*, which matters far more than size. Sizes are the real download, measured from the model's own file listing. Quality ranks are the direct LMArena row for the exact base model on the date named; a family stand-in never inherits a score.

### 16 GB

| Class | Model | Download | Working set | Speed | Agency baseline | Evidence |
| --- | --- | ---: | ---: | --- | --- | --- |
| day (one model for both) | **Gemma 3 4B IT (language-model-only export) 4-bit** (Flow's pick) | 2.6 GB | 4.6 GB | 91 tok/s, 1.6 s to first token | Meets it (8 of 8) | measured on 32 to 36 GB; projected here |
| day (one model for both) | Mistral 7B Instruct v0.2 4-bit | 4.3 GB | 6.4 GB | 57 tok/s, 2.8 s to first token | Meets it (8 of 8) | measured on 32 to 36 GB; projected here |
| night (one model for both) | Gemma 3 4B IT (language-model-only export) 4-bit | 2.6 GB | 4.6 GB | 91 tok/s, 1.6 s to first token | Not yet (0 of 3) | measured on 32 to 36 GB; projected here |
| night (one model for both) | Mistral 7B Instruct v0.2 4-bit | 4.3 GB | 6.4 GB | 57 tok/s, 2.8 s to first token | Not yet (0 of 3) | measured on 32 to 36 GB; projected here |
| night | *No pick yet* | | | | No night model has earned the pick yet; Mistral 7B Instruct v0.2 4-bit is the leading candidate at 0 of 3 | |

### 24 GB

| Class | Model | Download | Working set | Speed | Agency baseline | Evidence |
| --- | --- | ---: | ---: | --- | --- | --- |
| day (one model for both) | Gemma 3 4B IT (language-model-only export) 4-bit | 2.6 GB | 4.6 GB | 91 tok/s, 1.6 s to first token | Meets it (8 of 8) | measured on 32 to 36 GB; projected here |
| day (one model for both) | Mistral 7B Instruct v0.2 4-bit | 4.3 GB | 6.4 GB | 57 tok/s, 2.8 s to first token | Meets it (8 of 8) | measured on 32 to 36 GB; projected here |
| day | **Llama 3.1 8B Instruct 4-bit** (Flow's pick) | 4.5 GB | 6.5 GB | 55 tok/s, 2.8 s to first token | Meets it (8 of 8) | measured on 32 to 36 GB; projected here |
| day | Granite 4.1 8B 4-bit | 5.2 GB | 7.0 GB | 45 tok/s, 3.5 s to first token (below the day speed floor) | Not run | measured on 32 to 36 GB; projected here |
| day | Gemma 3n E4B IT (language-model-only export) 4-bit | 3.9 GB | 7.2 GB | 61 tok/s, 2.3 s to first token | Not run | measured on 32 to 36 GB; projected here |
| night (one model for both) | Gemma 3 4B IT (language-model-only export) 4-bit | 2.6 GB | 4.6 GB | 91 tok/s, 1.6 s to first token | Not yet (0 of 3) | measured on 32 to 36 GB; projected here |
| night (one model for both) | Mistral 7B Instruct v0.2 4-bit | 4.3 GB | 6.4 GB | 57 tok/s, 2.8 s to first token | Not yet (0 of 3) | measured on 32 to 36 GB; projected here |
| night | *No pick yet* | | | | No night model has earned the pick yet; Mistral 7B Instruct v0.2 4-bit is the leading candidate at 0 of 3 | |

### 32 to 36 GB

| Class | Model | Download | Working set | Speed | Agency baseline | Evidence |
| --- | --- | ---: | ---: | --- | --- | --- |
| day (one model for both) | Gemma 3 4B IT (language-model-only export) 4-bit | 2.6 GB | 4.6 GB | 91 tok/s, 1.6 s to first token | Meets it (8 of 8) | measured |
| day (one model for both) | Mistral 7B Instruct v0.2 4-bit | 4.3 GB | 6.4 GB | 57 tok/s, 2.8 s to first token | Meets it (8 of 8) | measured |
| day | **Llama 3.1 8B Instruct 4-bit** (Flow's pick) | 4.5 GB | 6.5 GB | 55 tok/s, 2.8 s to first token | Meets it (8 of 8) | measured |
| day | Granite 4.1 8B 4-bit | 5.2 GB | 7.0 GB | 45 tok/s, 3.5 s to first token (below the day speed floor) | Not run | measured |
| day | Gemma 3n E4B IT (language-model-only export) 4-bit | 3.9 GB | 7.2 GB | 61 tok/s, 2.3 s to first token | Not run | measured |
| day | Gemma 3 12B IT (language-model-only export) 4-bit | 7.2 GB | 10.4 GB | 34 tok/s, 5.1 s to first token (below the day speed floor) | Not yet (1 of 8) | measured |
| night (one model for both) | Gemma 3 4B IT (language-model-only export) 4-bit | 2.6 GB | 4.6 GB | 91 tok/s, 1.6 s to first token | Not yet (0 of 3) | measured |
| night (one model for both) | Mistral 7B Instruct v0.2 4-bit | 4.3 GB | 6.4 GB | 57 tok/s, 2.8 s to first token | Not yet (0 of 3) | measured |
| night | **Gemma 4 26B A4B IT 4-bit** (Flow's pick) | 15.4 GB | 18.1 GB | 76 tok/s, 1.8 s to first token | Meets it (7 of 8) | measured |
| night | Qwen 3.8 27B 4-bit | 16.1 GB | 19.1 GB | 17 tok/s, 11.1 s to first token | Meets it (8 of 8) | measured |

### 48 to 64 GB

| Class | Model | Download | Working set | Speed | Agency baseline | Evidence |
| --- | --- | ---: | ---: | --- | --- | --- |
| day (one model for both) | Gemma 3 4B IT (language-model-only export) 4-bit | 2.6 GB | 4.6 GB | 91 tok/s, 1.6 s to first token | Meets it (8 of 8) | measured on 32 to 36 GB; projected here |
| day (one model for both) | Mistral 7B Instruct v0.2 4-bit | 4.3 GB | 6.4 GB | 57 tok/s, 2.8 s to first token | Meets it (8 of 8) | measured on 32 to 36 GB; projected here |
| day | **Llama 3.1 8B Instruct 4-bit** (Flow's pick) | 4.5 GB | 6.5 GB | 55 tok/s, 2.8 s to first token | Meets it (8 of 8) | measured on 32 to 36 GB; projected here |
| day | Granite 4.1 8B 4-bit | 5.2 GB | 7.0 GB | 45 tok/s, 3.5 s to first token (below the day speed floor) | Not run | measured on 32 to 36 GB; projected here |
| day | Gemma 3n E4B IT (language-model-only export) 4-bit | 3.9 GB | 7.2 GB | 61 tok/s, 2.3 s to first token | Not run | measured on 32 to 36 GB; projected here |
| day | Gemma 3 12B IT (language-model-only export) 4-bit | 7.2 GB | 10.4 GB | 34 tok/s, 5.1 s to first token (below the day speed floor) | Not yet (1 of 8) | measured on 32 to 36 GB; projected here |
| night (one model for both) | Gemma 3 4B IT (language-model-only export) 4-bit | 2.6 GB | 4.6 GB | 91 tok/s, 1.6 s to first token | Not yet (0 of 3) | measured on 32 to 36 GB; projected here |
| night (one model for both) | Mistral 7B Instruct v0.2 4-bit | 4.3 GB | 6.4 GB | 57 tok/s, 2.8 s to first token | Not yet (0 of 3) | measured on 32 to 36 GB; projected here |
| night | **Gemma 4 26B A4B IT 4-bit** (Flow's pick) | 15.4 GB | 18.1 GB | 76 tok/s, 1.8 s to first token | Meets it (7 of 8) | measured on 32 to 36 GB; projected here |
| night | Qwen 3.8 27B 4-bit | 16.1 GB | 19.1 GB | 17 tok/s, 11.1 s to first token | Meets it (8 of 8) | measured on 32 to 36 GB; projected here |

### 96 to 128 GB

| Class | Model | Download | Working set | Speed | Agency baseline | Evidence |
| --- | --- | ---: | ---: | --- | --- | --- |
| day (one model for both) | Gemma 3 4B IT (language-model-only export) 4-bit | 2.6 GB | 4.6 GB | 91 tok/s, 1.6 s to first token | Meets it (8 of 8) | measured on 32 to 36 GB; projected here |
| day (one model for both) | Mistral 7B Instruct v0.2 4-bit | 4.3 GB | 6.4 GB | 57 tok/s, 2.8 s to first token | Meets it (8 of 8) | measured on 32 to 36 GB; projected here |
| day | **Llama 3.1 8B Instruct 4-bit** (Flow's pick) | 4.5 GB | 6.5 GB | 55 tok/s, 2.8 s to first token | Meets it (8 of 8) | measured on 32 to 36 GB; projected here |
| day | Granite 4.1 8B 4-bit | 5.2 GB | 7.0 GB | 45 tok/s, 3.5 s to first token (below the day speed floor) | Not run | measured on 32 to 36 GB; projected here |
| day | Gemma 3n E4B IT (language-model-only export) 4-bit | 3.9 GB | 7.2 GB | 61 tok/s, 2.3 s to first token | Not run | measured on 32 to 36 GB; projected here |
| day | Gemma 3 12B IT (language-model-only export) 4-bit | 7.2 GB | 10.4 GB | 34 tok/s, 5.1 s to first token (below the day speed floor) | Not yet (1 of 8) | measured on 32 to 36 GB; projected here |
| night (one model for both) | Gemma 3 4B IT (language-model-only export) 4-bit | 2.6 GB | 4.6 GB | 91 tok/s, 1.6 s to first token | Not yet (0 of 3) | measured on 32 to 36 GB; projected here |
| night (one model for both) | Mistral 7B Instruct v0.2 4-bit | 4.3 GB | 6.4 GB | 57 tok/s, 2.8 s to first token | Not yet (0 of 3) | measured on 32 to 36 GB; projected here |
| night | **Gemma 4 26B A4B IT 4-bit** (Flow's pick) | 15.4 GB | 18.1 GB | 76 tok/s, 1.8 s to first token | Meets it (7 of 8) | measured on 32 to 36 GB; projected here |
| night | Qwen 3.8 27B 4-bit | 16.1 GB | 19.1 GB | 17 tok/s, 11.1 s to first token | Meets it (8 of 8) | measured on 32 to 36 GB; projected here |

### 256 GB and up

| Class | Model | Download | Working set | Speed | Agency baseline | Evidence |
| --- | --- | ---: | ---: | --- | --- | --- |
| day (one model for both) | Gemma 3 4B IT (language-model-only export) 4-bit | 2.6 GB | 4.6 GB | 91 tok/s, 1.6 s to first token | Meets it (8 of 8) | measured on 32 to 36 GB; projected here |
| day (one model for both) | Mistral 7B Instruct v0.2 4-bit | 4.3 GB | 6.4 GB | 57 tok/s, 2.8 s to first token | Meets it (8 of 8) | measured on 32 to 36 GB; projected here |
| day | **Llama 3.1 8B Instruct 4-bit** (Flow's pick) | 4.5 GB | 6.5 GB | 55 tok/s, 2.8 s to first token | Meets it (8 of 8) | measured on 32 to 36 GB; projected here |
| day | Granite 4.1 8B 4-bit | 5.2 GB | 7.0 GB | 45 tok/s, 3.5 s to first token (below the day speed floor) | Not run | measured on 32 to 36 GB; projected here |
| day | Gemma 3n E4B IT (language-model-only export) 4-bit | 3.9 GB | 7.2 GB | 61 tok/s, 2.3 s to first token | Not run | measured on 32 to 36 GB; projected here |
| day | Gemma 3 12B IT (language-model-only export) 4-bit | 7.2 GB | 10.4 GB | 34 tok/s, 5.1 s to first token (below the day speed floor) | Not yet (1 of 8) | measured on 32 to 36 GB; projected here |
| night (one model for both) | Gemma 3 4B IT (language-model-only export) 4-bit | 2.6 GB | 4.6 GB | 91 tok/s, 1.6 s to first token | Not yet (0 of 3) | measured on 32 to 36 GB; projected here |
| night (one model for both) | Mistral 7B Instruct v0.2 4-bit | 4.3 GB | 6.4 GB | 57 tok/s, 2.8 s to first token | Not yet (0 of 3) | measured on 32 to 36 GB; projected here |
| night | **Gemma 4 26B A4B IT 4-bit** (Flow's pick) | 15.4 GB | 18.1 GB | 76 tok/s, 1.8 s to first token | Meets it (7 of 8) | measured on 32 to 36 GB; projected here |
| night | Qwen 3.8 27B 4-bit | 16.1 GB | 19.1 GB | 17 tok/s, 11.1 s to first token | Meets it (8 of 8) | measured on 32 to 36 GB; projected here |

Every list row, every measurement cell and every baseline run behind these tables, probe by probe, is in [[Model Curation and Measurements]]. For repeatable Flow Runtime measurements on named Mac hardware, see [[Curated Model Comparisons]]. Those comparisons are unranked evidence, not another recommendation list.

## Flow keeps this list current

This document updates itself along with the rest of this folder, so the list reflects what is worth running today rather than what was worth running when you installed Flow.

The list above was researched on 9 September 2026. Flow's release check refuses to cut a release whose list is more than thirty days old, so a list that has gone stale is a release that did not happen, not a list you have to notice.

**Your edits are safe.** If you change this document, Flow does not overwrite it. It offers you the update and lets you decide, the same as any other document here.

## Downloading is not the last step

A model that runs is not yet a model Flow knows how to use well. Once one is on your Mac, **measure it**: Flow times it against a fixed piece of work and records the result. That measurement is what lets Flow choose the right model for each task instead of guessing from size.

Flow will propose the measurement itself once there is something to measure.
