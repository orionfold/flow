---
title: Models Flow Recommends
tags: [flow, models, agency]
catalogueVersion: 4
researched: 2026-09-12
models:
  - id: mlx-community/gemma-3-text-4b-it-4bit
    displayName: Gemma 3 4B IT (language-model-only export) 4-bit
    format: mlx
    weightBytes: 2600191231
    agencyBaseline: flow-agency-v2
    class: both
    tiers: [16, 24, 32-36, 48-64, 96-128, 256+]
    dayPickTiers: [16]
    nightPickTiers: []
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
    note: Composes 8 of 8 on Flow's agency baseline in one turn; 91 tokens a second, 1.6 s to the first word (calculated).
  - id: mlx-community/Mistral-7B-Instruct-v0.2-4bit
    displayName: Mistral 7B Instruct v0.2 4-bit
    format: mlx
    weightBytes: 4264704510
    agencyBaseline: flow-agency-v2
    class: both
    tiers: [16, 24, 32-36, 48-64, 96-128, 256+]
    dayPickTiers: []
    nightPickTiers: []
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
    note: Composes 8 of 8 on Flow's agency baseline in one turn; 57 tokens a second, 2.8 s to the first word (calculated).
  - id: mlx-community/Llama-3.1-8B-Instruct-4bit
    displayName: Llama 3.1 8B Instruct 4-bit
    format: mlx
    weightBytes: 4534824337
    agencyBaseline: flow-agency-v2
    class: day
    tiers: [24, 32-36, 48-64, 96-128, 256+]
    dayPickTiers: []
    nightPickTiers: []
    revision: 90215b22ec18e72f623dde2ea7af4097025160e2
    servedWindow: 8192
    kvBytesPerToken: 131072
    workingSetBytes: 6505255328
    evidence: measured
    evidenceSource: signed receipt c8413aaf1c3c480fbbd533f29a84027be7533687d2527a07ce577115a9911f97
    tokensPerSecond: 54.6
    timeToFirstTokenSeconds: 2.8
    baselineComposed: 8
    baselineProbeCount: 8
    dayBaselineComposed: 8
    dayBaselineProbeCount: 8
    nightBaselineComposed: 1
    nightBaselineProbeCount: 3
    measuredTier: 32-36
    qualitySource: LMArena lmarena-ai/leaderboard-dataset text_style_control/latest, published 2026-09-02
    note: Composes 8 of 8 on Flow's agency baseline in one turn; 55 tokens a second, 2.8 s to the first word (calculated).
  - id: mlx-community/gemma-4-e4b-it-4bit
    displayName: Gemma 4 E4B IT 4-bit
    format: mlx
    weightBytes: 5179241512
    agencyBaseline: flow-agency-v2
    class: day
    tiers: [24, 32-36, 48-64, 96-128, 256+]
    dayPickTiers: [24, 32-36, 48-64, 96-128, 256+]
    nightPickTiers: []
    revision: 475b9088d29754a3379866cf5aeb6b41acd313c2
    servedWindow: 8192
    kvBytesPerToken: 86016
    workingSetBytes: 6598185544
    evidence: measured
    evidenceSource: signed receipt c8413aaf1c3c480fbbd533f29a84027be7533687d2527a07ce577115a9911f97
    tokensPerSecond: 71.9
    timeToFirstTokenSeconds: 1.1
    baselineComposed: 8
    baselineProbeCount: 8
    dayBaselineComposed: 8
    dayBaselineProbeCount: 8
    nightBaselineComposed: 3
    nightBaselineProbeCount: 8
    measuredTier: 32-36
    qualitySource: Flow job comparison e4b-over-llama-day-20260912; no direct Arena rank
    note: Composes 8 of 8 on Flow's agency baseline in one turn; 72 tokens a second, 1.1 s to the first word (calculated).
  - id: mlx-community/granite-4.1-8b-4bit
    displayName: Granite 4.1 8B 4-bit
    format: mlx
    weightBytes: 5245635681
    agencyBaseline: none
    class: day
    tiers: [24, 32-36, 48-64, 96-128, 256+]
    dayPickTiers: []
    nightPickTiers: []
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
    note: Loads and runs on Flow Runtime; the agency baseline has not been run on it; 45 tokens a second, 3.5 s to the first word (calculated); below the day speed floor.
  - id: mlx-community/gemma-3n-E4B-it-lm-4bit
    displayName: Gemma 3n E4B IT (language-model-only export) 4-bit
    format: mlx
    weightBytes: 3903219922
    agencyBaseline: none
    class: day
    tiers: [24, 32-36, 48-64, 96-128, 256+]
    dayPickTiers: []
    nightPickTiers: []
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
    note: Loads and runs on Flow Runtime; the agency baseline has not been run on it; 61 tokens a second, 2.3 s to the first word (calculated).
  - id: mlx-community/gemma-3-text-12b-it-4bit
    displayName: Gemma 3 12B IT (language-model-only export) 4-bit
    format: mlx
    weightBytes: 7225400219
    agencyBaseline: none
    class: day
    tiers: [32-36, 48-64, 96-128, 256+]
    dayPickTiers: []
    nightPickTiers: []
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
    note: Composes 1 of 8 on Flow's agency baseline in one turn, so not yet a pick; 34 tokens a second, 5.1 s to the first word (calculated); below the day speed floor.
  - id: mlx-community/gemma-4-26b-a4b-it-4bit
    displayName: Gemma 4 26B A4B IT 4-bit
    format: mlx
    weightBytes: 15373588575
    agencyBaseline: flow-agency-v2
    class: night
    tiers: [32-36, 48-64, 96-128, 256+]
    dayPickTiers: []
    nightPickTiers: [32-36, 48-64, 96-128, 256+]
    revision: 0d77464eeb233a2da68ebf9d7dc4edaac7db956d
    servedWindow: 8192
    kvBytesPerToken: 245760
    workingSetBytes: 18120650872
    evidence: measured
    evidenceSource: signed receipt c8413aaf1c3c480fbbd533f29a84027be7533687d2527a07ce577115a9911f97
    tokensPerSecond: 75.0
    timeToFirstTokenSeconds: 1.9
    baselineComposed: 8
    baselineProbeCount: 8
    nightBaselineComposed: 8
    nightBaselineProbeCount: 8
    measuredTier: 32-36
    qualitySource: LMArena lmarena-ai/leaderboard-dataset text_style_control/latest, published 2026-09-02
    note: Composes 8 of 8 on Flow's agency baseline with its own lookups; 75 tokens a second, 1.9 s to the first word (calculated).
  - id: mlx-community/Qwen3.8-27B-4bit
    displayName: Qwen 3.8 27B 4-bit
    format: mlx
    weightBytes: 16081490933
    agencyBaseline: flow-agency-v2
    class: night
    tiers: [32-36, 48-64, 96-128, 256+]
    dayPickTiers: []
    nightPickTiers: []
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
    note: Composes 8 of 8 on Flow's agency baseline with its own lookups; 17 tokens a second, 11.1 s to the first word (calculated).
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

Flow keeps two picks for a Mac. The **day model** sits beside your work and answers while you are typing, so it is judged on how fast its first word arrives and held to a third of your Mac's memory. The **night model** has the Mac to itself for the Night Shift, so it is judged on accuracy and on how much it can read at once, and may take three fifths of memory. A smaller Mac may have no qualified Night pick; each class must pass its own baseline.

## What "fits" means

Flow reads your Mac's actual memory rather than looking your model up in a table. A MacBook Pro 14" ships in several memory configurations, so the name on the box does not answer the question; the number does.

A model's weights are not the whole cost. The context you give it, the helper's own buffers and the rest of macOS all need room too. Flow judges the **working set**, the memory the helper actually holds with the model loaded and a document in front of it, against each class's budget. It also checks free disk space, since a download that leaves your volume full is one you pay for twice.

Flow's **agency baseline** is eight fixed tasks run through its own loop on Flow Runtime. A new pick must pass all eight and meet its class's speed, download and memory limits. An eligible existing pick stays until a qualified challenger produces better work in repeated document jobs judged for correctness, source fidelity and usefulness. Day favors speed when quality is comparable; Night favors job quality. Ideas, Settings and automatic Flow Runtime routing use these published choices. Your explicit model choices and routing rules still apply.

If the published pick is unavailable or does not fit your Mac, **Flow says so**. It does not promote another model merely because it is smaller. You can choose another available model or configure a metered account.

## Measured, or projected

Every number in the tables below says how it knows. **Measured** rows were run on a 36 GB MacBook Pro with an Apple M3 Max, through Flow Runtime, with the receipt signed by Orionfold; the numbers are that Mac's, not yours. **Projected** means the working set is computed from the model's own files; speed may have been measured separately, as the row says. These rows fill cells that lack a measured candidate. A projected row is never a pick.

## Why these picks

**Day · 12 September 2026 · 24 GB, 32 to 36 GB, 48 to 64 GB, 96 to 128 GB, 256 GB and up:** Gemma 4 E4B replaces Llama 3.1 8B for Day work. Two blinded reviews preferred its source fidelity across four document briefs, each repeated three times. Llama incorrectly denied a comparison group supplied by the source; E4B preserved it. Both passed all eight Day baseline tasks, and E4B met the speed and memory limits. These are four scenarios, not a general quality benchmark; E4B still needs clearer approval-status wording in one brief. Its Night baseline was 3 of 8, so the Night pick is unchanged. Reasoning remains Recommended.

## The tables, by memory

The models use MLX directories or single GGUF files, as each row states, and are instruct-tuned. Download sizes come from the pinned file listing. Where an exact base model has direct LMArena evidence, its dated rank is shown as external context. Flow can also admit a model through a qualified comparison of actual Flow jobs. Publisher benchmarks, external ranks and Flow's own measurements remain separate evidence; a family stand-in never inherits a score.

**Format and dialect.** The Format column describes this build's engine capability. Both owned engines constrain supported output shapes when a run requests them; a run without a requested shape remains unconstrained. The measurements and baseline results below keep their original runtime and envelope. Earlier prompt-only MLX runs have not been remeasured by this runtime update; their recorded dialect remains in [[Model Curation and Measurements]]. Flow still validates every result before using it.

### 16 GB

| Class | Model | Format | Download | Working set | Speed | Agency baseline | Evidence |
| --- | --- | --- | ---: | ---: | --- | --- | --- |
| day (candidate for both) | **Gemma 3 4B IT (language-model-only export) 4-bit** (Flow's pick) | MLX, grammar dialect | 2.6 GB | 4.6 GB | 91 tok/s, 1.6 s to first word (calculated) | Meets it (8 of 8) | measured on 32 to 36 GB; projected here |
| day (candidate for both) | Mistral 7B Instruct v0.2 4-bit | MLX, grammar dialect | 4.3 GB | 6.4 GB | 57 tok/s, 2.8 s to first word (calculated) | Meets it (8 of 8) | measured on 32 to 36 GB; projected here |
| night (candidate for both) | Gemma 3 4B IT (language-model-only export) 4-bit | MLX, grammar dialect | 2.6 GB | 4.6 GB | 91 tok/s, 1.6 s to first word (calculated) | Not yet (0 of 3) | measured on 32 to 36 GB; projected here |
| night (candidate for both) | Mistral 7B Instruct v0.2 4-bit | MLX, grammar dialect | 4.3 GB | 6.4 GB | 57 tok/s, 2.8 s to first word (calculated) | Not yet (0 of 3) | measured on 32 to 36 GB; projected here |
| night | *No pick yet* | | | | | No night model has earned the pick yet; Mistral 7B Instruct v0.2 4-bit is the leading candidate at 0 of 3 | |

### 24 GB

| Class | Model | Format | Download | Working set | Speed | Agency baseline | Evidence |
| --- | --- | --- | ---: | ---: | --- | --- | --- |
| day (candidate for both) | Gemma 3 4B IT (language-model-only export) 4-bit | MLX, grammar dialect | 2.6 GB | 4.6 GB | 91 tok/s, 1.6 s to first word (calculated) | Meets it (8 of 8) | measured on 32 to 36 GB; projected here |
| day (candidate for both) | Mistral 7B Instruct v0.2 4-bit | MLX, grammar dialect | 4.3 GB | 6.4 GB | 57 tok/s, 2.8 s to first word (calculated) | Meets it (8 of 8) | measured on 32 to 36 GB; projected here |
| day | Llama 3.1 8B Instruct 4-bit | MLX, grammar dialect | 4.5 GB | 6.5 GB | 55 tok/s, 2.8 s to first word (calculated) | Meets it (8 of 8) | measured on 32 to 36 GB; projected here |
| day | **Gemma 4 E4B IT 4-bit** (Flow's pick) | MLX, grammar dialect | 5.2 GB | 6.6 GB | 72 tok/s, 1.1 s to first word (calculated) | Meets it (8 of 8) | measured on 32 to 36 GB; projected here |
| day | Granite 4.1 8B 4-bit | MLX, grammar dialect | 5.2 GB | 7.0 GB | 45 tok/s, 3.5 s to first word (calculated) (below the day speed floor) | Not run | measured on 32 to 36 GB; projected here |
| day | Gemma 3n E4B IT (language-model-only export) 4-bit | MLX, grammar dialect | 3.9 GB | 7.2 GB | 61 tok/s, 2.3 s to first word (calculated) | Not run | measured on 32 to 36 GB; projected here |
| night (candidate for both) | Gemma 3 4B IT (language-model-only export) 4-bit | MLX, grammar dialect | 2.6 GB | 4.6 GB | 91 tok/s, 1.6 s to first word (calculated) | Not yet (0 of 3) | measured on 32 to 36 GB; projected here |
| night (candidate for both) | Mistral 7B Instruct v0.2 4-bit | MLX, grammar dialect | 4.3 GB | 6.4 GB | 57 tok/s, 2.8 s to first word (calculated) | Not yet (0 of 3) | measured on 32 to 36 GB; projected here |
| night | *No pick yet* | | | | | No night model has earned the pick yet; Mistral 7B Instruct v0.2 4-bit is the leading candidate at 0 of 3 | |

### 32 to 36 GB

| Class | Model | Format | Download | Working set | Speed | Agency baseline | Evidence |
| --- | --- | --- | ---: | ---: | --- | --- | --- |
| day (candidate for both) | Gemma 3 4B IT (language-model-only export) 4-bit | MLX, grammar dialect | 2.6 GB | 4.6 GB | 91 tok/s, 1.6 s to first word (calculated) | Meets it (8 of 8) | measured |
| day (candidate for both) | Mistral 7B Instruct v0.2 4-bit | MLX, grammar dialect | 4.3 GB | 6.4 GB | 57 tok/s, 2.8 s to first word (calculated) | Meets it (8 of 8) | measured |
| day | Llama 3.1 8B Instruct 4-bit | MLX, grammar dialect | 4.5 GB | 6.5 GB | 55 tok/s, 2.8 s to first word (calculated) | Meets it (8 of 8) | measured |
| day | **Gemma 4 E4B IT 4-bit** (Flow's pick) | MLX, grammar dialect | 5.2 GB | 6.6 GB | 72 tok/s, 1.1 s to first word (calculated) | Meets it (8 of 8) | measured |
| day | Granite 4.1 8B 4-bit | MLX, grammar dialect | 5.2 GB | 7.0 GB | 45 tok/s, 3.5 s to first word (calculated) (below the day speed floor) | Not run | measured |
| day | Gemma 3n E4B IT (language-model-only export) 4-bit | MLX, grammar dialect | 3.9 GB | 7.2 GB | 61 tok/s, 2.3 s to first word (calculated) | Not run | measured |
| day | Gemma 3 12B IT (language-model-only export) 4-bit | MLX, grammar dialect | 7.2 GB | 10.4 GB | 34 tok/s, 5.1 s to first word (calculated) (below the day speed floor) | Not yet (1 of 8) | measured |
| night (candidate for both) | Gemma 3 4B IT (language-model-only export) 4-bit | MLX, grammar dialect | 2.6 GB | 4.6 GB | 91 tok/s, 1.6 s to first word (calculated) | Not yet (0 of 3) | measured |
| night (candidate for both) | Mistral 7B Instruct v0.2 4-bit | MLX, grammar dialect | 4.3 GB | 6.4 GB | 57 tok/s, 2.8 s to first word (calculated) | Not yet (0 of 3) | measured |
| night | **Gemma 4 26B A4B IT 4-bit** (Flow's pick) | MLX, grammar dialect | 15.4 GB | 18.1 GB | 75 tok/s, 1.9 s to first word (calculated) | Meets it (8 of 8) | measured |
| night | Qwen 3.8 27B 4-bit | MLX, grammar dialect | 16.1 GB | 19.1 GB | 17 tok/s, 11.1 s to first word (calculated) | Meets it (8 of 8) | measured |

### 48 to 64 GB

| Class | Model | Format | Download | Working set | Speed | Agency baseline | Evidence |
| --- | --- | --- | ---: | ---: | --- | --- | --- |
| day (candidate for both) | Gemma 3 4B IT (language-model-only export) 4-bit | MLX, grammar dialect | 2.6 GB | 4.6 GB | 91 tok/s, 1.6 s to first word (calculated) | Meets it (8 of 8) | measured on 32 to 36 GB; projected here |
| day (candidate for both) | Mistral 7B Instruct v0.2 4-bit | MLX, grammar dialect | 4.3 GB | 6.4 GB | 57 tok/s, 2.8 s to first word (calculated) | Meets it (8 of 8) | measured on 32 to 36 GB; projected here |
| day | Llama 3.1 8B Instruct 4-bit | MLX, grammar dialect | 4.5 GB | 6.5 GB | 55 tok/s, 2.8 s to first word (calculated) | Meets it (8 of 8) | measured on 32 to 36 GB; projected here |
| day | **Gemma 4 E4B IT 4-bit** (Flow's pick) | MLX, grammar dialect | 5.2 GB | 6.6 GB | 72 tok/s, 1.1 s to first word (calculated) | Meets it (8 of 8) | measured on 32 to 36 GB; projected here |
| day | Granite 4.1 8B 4-bit | MLX, grammar dialect | 5.2 GB | 7.0 GB | 45 tok/s, 3.5 s to first word (calculated) (below the day speed floor) | Not run | measured on 32 to 36 GB; projected here |
| day | Gemma 3n E4B IT (language-model-only export) 4-bit | MLX, grammar dialect | 3.9 GB | 7.2 GB | 61 tok/s, 2.3 s to first word (calculated) | Not run | measured on 32 to 36 GB; projected here |
| day | Gemma 3 12B IT (language-model-only export) 4-bit | MLX, grammar dialect | 7.2 GB | 10.4 GB | 34 tok/s, 5.1 s to first word (calculated) (below the day speed floor) | Not yet (1 of 8) | measured on 32 to 36 GB; projected here |
| night (candidate for both) | Gemma 3 4B IT (language-model-only export) 4-bit | MLX, grammar dialect | 2.6 GB | 4.6 GB | 91 tok/s, 1.6 s to first word (calculated) | Not yet (0 of 3) | measured on 32 to 36 GB; projected here |
| night (candidate for both) | Mistral 7B Instruct v0.2 4-bit | MLX, grammar dialect | 4.3 GB | 6.4 GB | 57 tok/s, 2.8 s to first word (calculated) | Not yet (0 of 3) | measured on 32 to 36 GB; projected here |
| night | **Gemma 4 26B A4B IT 4-bit** (Flow's pick) | MLX, grammar dialect | 15.4 GB | 18.1 GB | 75 tok/s, 1.9 s to first word (calculated) | Meets it (8 of 8) | measured on 32 to 36 GB; projected here |
| night | Qwen 3.8 27B 4-bit | MLX, grammar dialect | 16.1 GB | 19.1 GB | 17 tok/s, 11.1 s to first word (calculated) | Meets it (8 of 8) | measured on 32 to 36 GB; projected here |

### 96 to 128 GB

| Class | Model | Format | Download | Working set | Speed | Agency baseline | Evidence |
| --- | --- | --- | ---: | ---: | --- | --- | --- |
| day (candidate for both) | Gemma 3 4B IT (language-model-only export) 4-bit | MLX, grammar dialect | 2.6 GB | 4.6 GB | 91 tok/s, 1.6 s to first word (calculated) | Meets it (8 of 8) | measured on 32 to 36 GB; projected here |
| day (candidate for both) | Mistral 7B Instruct v0.2 4-bit | MLX, grammar dialect | 4.3 GB | 6.4 GB | 57 tok/s, 2.8 s to first word (calculated) | Meets it (8 of 8) | measured on 32 to 36 GB; projected here |
| day | Llama 3.1 8B Instruct 4-bit | MLX, grammar dialect | 4.5 GB | 6.5 GB | 55 tok/s, 2.8 s to first word (calculated) | Meets it (8 of 8) | measured on 32 to 36 GB; projected here |
| day | **Gemma 4 E4B IT 4-bit** (Flow's pick) | MLX, grammar dialect | 5.2 GB | 6.6 GB | 72 tok/s, 1.1 s to first word (calculated) | Meets it (8 of 8) | measured on 32 to 36 GB; projected here |
| day | Granite 4.1 8B 4-bit | MLX, grammar dialect | 5.2 GB | 7.0 GB | 45 tok/s, 3.5 s to first word (calculated) (below the day speed floor) | Not run | measured on 32 to 36 GB; projected here |
| day | Gemma 3n E4B IT (language-model-only export) 4-bit | MLX, grammar dialect | 3.9 GB | 7.2 GB | 61 tok/s, 2.3 s to first word (calculated) | Not run | measured on 32 to 36 GB; projected here |
| day | Gemma 3 12B IT (language-model-only export) 4-bit | MLX, grammar dialect | 7.2 GB | 10.4 GB | 34 tok/s, 5.1 s to first word (calculated) (below the day speed floor) | Not yet (1 of 8) | measured on 32 to 36 GB; projected here |
| night (candidate for both) | Gemma 3 4B IT (language-model-only export) 4-bit | MLX, grammar dialect | 2.6 GB | 4.6 GB | 91 tok/s, 1.6 s to first word (calculated) | Not yet (0 of 3) | measured on 32 to 36 GB; projected here |
| night (candidate for both) | Mistral 7B Instruct v0.2 4-bit | MLX, grammar dialect | 4.3 GB | 6.4 GB | 57 tok/s, 2.8 s to first word (calculated) | Not yet (0 of 3) | measured on 32 to 36 GB; projected here |
| night | **Gemma 4 26B A4B IT 4-bit** (Flow's pick) | MLX, grammar dialect | 15.4 GB | 18.1 GB | 75 tok/s, 1.9 s to first word (calculated) | Meets it (8 of 8) | measured on 32 to 36 GB; projected here |
| night | Qwen 3.8 27B 4-bit | MLX, grammar dialect | 16.1 GB | 19.1 GB | 17 tok/s, 11.1 s to first word (calculated) | Meets it (8 of 8) | measured on 32 to 36 GB; projected here |

### 256 GB and up

| Class | Model | Format | Download | Working set | Speed | Agency baseline | Evidence |
| --- | --- | --- | ---: | ---: | --- | --- | --- |
| day (candidate for both) | Gemma 3 4B IT (language-model-only export) 4-bit | MLX, grammar dialect | 2.6 GB | 4.6 GB | 91 tok/s, 1.6 s to first word (calculated) | Meets it (8 of 8) | measured on 32 to 36 GB; projected here |
| day (candidate for both) | Mistral 7B Instruct v0.2 4-bit | MLX, grammar dialect | 4.3 GB | 6.4 GB | 57 tok/s, 2.8 s to first word (calculated) | Meets it (8 of 8) | measured on 32 to 36 GB; projected here |
| day | Llama 3.1 8B Instruct 4-bit | MLX, grammar dialect | 4.5 GB | 6.5 GB | 55 tok/s, 2.8 s to first word (calculated) | Meets it (8 of 8) | measured on 32 to 36 GB; projected here |
| day | **Gemma 4 E4B IT 4-bit** (Flow's pick) | MLX, grammar dialect | 5.2 GB | 6.6 GB | 72 tok/s, 1.1 s to first word (calculated) | Meets it (8 of 8) | measured on 32 to 36 GB; projected here |
| day | Granite 4.1 8B 4-bit | MLX, grammar dialect | 5.2 GB | 7.0 GB | 45 tok/s, 3.5 s to first word (calculated) (below the day speed floor) | Not run | measured on 32 to 36 GB; projected here |
| day | Gemma 3n E4B IT (language-model-only export) 4-bit | MLX, grammar dialect | 3.9 GB | 7.2 GB | 61 tok/s, 2.3 s to first word (calculated) | Not run | measured on 32 to 36 GB; projected here |
| day | Gemma 3 12B IT (language-model-only export) 4-bit | MLX, grammar dialect | 7.2 GB | 10.4 GB | 34 tok/s, 5.1 s to first word (calculated) (below the day speed floor) | Not yet (1 of 8) | measured on 32 to 36 GB; projected here |
| night (candidate for both) | Gemma 3 4B IT (language-model-only export) 4-bit | MLX, grammar dialect | 2.6 GB | 4.6 GB | 91 tok/s, 1.6 s to first word (calculated) | Not yet (0 of 3) | measured on 32 to 36 GB; projected here |
| night (candidate for both) | Mistral 7B Instruct v0.2 4-bit | MLX, grammar dialect | 4.3 GB | 6.4 GB | 57 tok/s, 2.8 s to first word (calculated) | Not yet (0 of 3) | measured on 32 to 36 GB; projected here |
| night | **Gemma 4 26B A4B IT 4-bit** (Flow's pick) | MLX, grammar dialect | 15.4 GB | 18.1 GB | 75 tok/s, 1.9 s to first word (calculated) | Meets it (8 of 8) | measured on 32 to 36 GB; projected here |
| night | Qwen 3.8 27B 4-bit | MLX, grammar dialect | 16.1 GB | 19.1 GB | 17 tok/s, 11.1 s to first word (calculated) | Meets it (8 of 8) | measured on 32 to 36 GB; projected here |

Every list row, every measurement cell and every baseline run behind these tables, probe by probe, is in [[Model Curation and Measurements]]. For repeatable Flow Runtime measurements on named Mac hardware, see [[Curated Model Comparisons]]. That page retains historical runtime measurements. They provide context for the current picks; a selection changes through the qualified Flow-job comparison described here.

## Flow keeps this list current

This document updates itself along with the rest of this folder, so the list reflects what is worth running today rather than what was worth running when you installed Flow.

The list above was researched on 12 September 2026. Flow's release check refuses to cut a release whose list is more than thirty days old, so a list that has gone stale is a release that did not happen, not a list you have to notice.

**Your edits are safe.** If you change this document, Flow does not overwrite it. It offers you the update and lets you decide, the same as any other document here.

## Downloading is not the last step

Once a model is on your Mac, **measure it**: Flow times it against a fixed piece of work and records the result. Your measurements help you compare responsiveness and can inform your routing rules. They do not silently replace Flow's published Day or Night pick.

Flow will propose the measurement itself once there is something to measure.
