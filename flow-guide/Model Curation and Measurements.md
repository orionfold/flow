---
title: Model Curation and Measurements
tags: [flow, models, agency, evidence]
researched: 2026-09-08
curator: Orionfold
---

# Model Curation and Measurements

This is the evidence behind [[Models Flow Recommends]], shown whole. That page keeps one outcome per model; this one keeps every list row, every measurement cell and every agency-check run with its three probes named and judged, each number beside the receipt it came from. Both pages are generated from the same files on the same date, so they cannot disagree.

Everything measured here was run on a 36 GB MacBook Pro with an Apple M3 Max (Mac15,10), through Flow Runtime, with the receipts signed by Orionfold. The numbers are that Mac's, not yours. The evidence was last assembled on 8 September 2026.

## How a model gets onto a list

Flow keeps two lists, one per class. A model is admitted by quality rank first, then by whether it can fit the class's share of memory and its download ceiling, then by whether Flow Runtime can load its files at all. Nothing on a list is a recommendation yet: a row becomes a pick only after it is measured and passes the agency baseline below.

### The day list (accepted 8 September 2026)

Quality ranks are from LMArena lmarena-ai/leaderboard-dataset text_style_control/latest, published 2026-09-02. To fit this class on the measured Mac a model's working set may take a third of memory, 12 GB here, its download may be at most 8.6 GB, and one model is loaded at a time. Flow Runtime's loaders were read from ml-explore/mlx-swift-lm at d7dc03d8, inspected 2026-09-08.

| # | Model | Download | Quality rank | Working set (projected) | Flow Runtime |
| ---: | --- | ---: | ---: | ---: | --- |
| 1 | Gemma 3 12B IT (language-model-only export) 4-bit | 7.2 GB | #217 (gemma-3-12b-it) | 12.9 GB (10.6 GB with a sliding cache) | loads and runs |
| 2 | Gemma 3n E4B IT (language-model-only export) 4-bit | 3.9 GB | #249 (gemma-3n-e4b-it) | 7.0 GB (6.5 GB with a sliding cache) | loads and runs |
| 3 | Granite 4.1 8B 4-bit | 5.2 GB | #264 (granite-4.1-8b) | 9.1 GB | loads and runs |
| 4 | Gemma 3 4B IT 4-bit (QAT) | 3.0 GB | #267 (gemma-3-4b-it) | 6.7 GB (5.8 GB with a sliding cache) | not yet run |
| 5 | Gemma 2 9B IT 4-bit | 5.2 GB | #296 (gemma-2-9b-it) | 10.5 GB (9.4 GB with a sliding cache) | not yet run |
| 6 | Phi-4 4-bit | 8.3 GB | #303 (phi-4) | 12.4 GB | not yet run |
| 7 | Ministral 8B Instruct 2410 4-bit | 4.5 GB | #309 (ministral-8b-2410) | 8.3 GB | not yet run |
| 8 | Llama 3.1 8B Instruct 4-bit | 4.5 GB | #326 (llama-3.1-8b-instruct) | 8.1 GB | not yet run |
| 9 | Gemma 2 2B IT 4-bit | 1.5 GB | #330 (gemma-2-2b-it) | 4.9 GB (4.5 GB with a sliding cache) | not yet run |
| 10 | Llama 3.2 3B Instruct 4-bit | 1.8 GB | #352 (llama-3.2-3b-instruct) | 5.3 GB | not yet run |

### The night list (accepted 8 September 2026)

Quality ranks are from LMArena lmarena-ai/leaderboard-dataset text_style_control/latest, published 2026-09-02. To fit this class on the measured Mac a model's working set may take three fifths of memory, 21 GB here, its download may be at most 25.8 GB, and one model is loaded at a time. Flow Runtime's loaders were read from ml-explore/mlx-swift-lm at d7dc03d8, inspected 2026-09-08.

| # | Model | Download | Quality rank | Working set (projected) | Flow Runtime |
| ---: | --- | ---: | ---: | ---: | --- |
| 1 | Gemma 4 31B IT 4-bit | 18.4 GB | #65 (gemma-4-31b) | 29.0 GB (23.1 GB with a sliding cache) | not yet run |
| 2 | Gemma 4 26B A4B IT 4-bit | 15.4 GB | #85 (gemma-4-26b-a4b) | 19.9 GB (18.4 GB with a sliding cache) | loads and runs |
| 3 | Qwen 3.8 27B 4-bit | 16.1 GB | #88 (qwen3.8-27b) | 20.7 GB | loads and runs |
| 4 | Muse Glimmer 30B 4-bit | 19.4 GB | #101 (muse-glimmer) | 22.4 GB (22.1 GB with a sliding cache) | not yet run |
| 5 | Qwen 3.5 27B 4-bit | 16.1 GB | #137 (qwen3.5-27b) | 20.7 GB | not yet run |
| 6 | Qwen 3.5 35B A3B 4-bit | 20.4 GB | #152 (qwen3.5-35b-a3b) | 23.6 GB | not yet run |
| 7 | Qwen 3 30B A3B Instruct 2507 4-bit | 17.2 GB | #170 (qwen3-30b-a3b-instruct-2507) | 20.5 GB | not yet run |
| 8 | GLM 4.7 Flash 4-bit | 16.9 GB | #183 (glm-4.7-flash) | 22.5 GB | not yet run |
| 9 | Gemma 3 27B IT 4-bit | 16.9 GB | #185 (gemma-3-27b-it) | 23.5 GB (20.5 GB with a sliding cache) | not yet run |
| 10 | Mistral Small 3.2 24B Instruct 2506 4-bit | 13.3 GB | #193 (mistral-small-2506) | 17.1 GB | not yet run |

## What was measured, cell by cell

A cohort loads one model at a time and runs the same two requests against it: **cold**, the first request after the model loads, and **warm**, the same request again with the model already resident. First word is the time to the first token; generation is the tokens a second after it; peak memory is the most the helper held during the request. Each cohort is one signed receipt, and its digest is on the heading. 21 cells in all.

### Cohort m3-max-36gb-0205t1-mlx-20260909-r2

3 cells per model, 100 seconds between cells, an 8192-token window, mlx-serve 0.1 on macOS 26.6, measured 9 September 2026. Signed receipt `b8f52fb8292ad1eb05233b2bb61c6f525bbe348eb245bd35dc29b7a47d482045`.

| Cell | Model | Cold: first word | Cold: generation | Cold: peak memory | Warm: first word | Warm: generation | Warm: peak memory |
| ---: | --- | ---: | ---: | ---: | ---: | ---: | ---: |
| 1 | Gemma 3n E4B IT (language-model-only export) 4-bit | 3.3 s | 62 tok/s | 6.4 GB | 2.3 s | 62 tok/s | 7.2 GB |
| 2 | Gemma 4 26B A4B IT 4-bit | 3.5 s | 76 tok/s | 17.8 GB | 1.8 s | 75 tok/s | 18.1 GB |
| 3 | Granite 4.1 8B 4-bit | 3.7 s | 45 tok/s | 6.8 GB | 3.5 s | 45 tok/s | 7.0 GB |
| 4 | Qwen 3.6 27B 4-bit | 11.2 s | 17 tok/s | 18.2 GB | 11.0 s | 17 tok/s | 19.1 GB |
| 5 | Qwen 3.8 27B 4-bit | 11.2 s | 17 tok/s | 18.3 GB | 11.2 s | 17 tok/s | 19.1 GB |
| 6 | Gemma 3n E4B IT (language-model-only export) 4-bit | 2.3 s | 62 tok/s | 6.4 GB | 2.3 s | 62 tok/s | 7.2 GB |
| 7 | Gemma 4 26B A4B IT 4-bit | 2.4 s | 75 tok/s | 17.8 GB | 1.8 s | 76 tok/s | 18.1 GB |
| 8 | Granite 4.1 8B 4-bit | 3.5 s | 45 tok/s | 6.8 GB | 3.5 s | 45 tok/s | 7.0 GB |
| 9 | Qwen 3.6 27B 4-bit | 11.1 s | 17 tok/s | 18.3 GB | 11.0 s | 17 tok/s | 19.1 GB |
| 10 | Qwen 3.8 27B 4-bit | 11.2 s | 17 tok/s | 18.3 GB | 11.1 s | 17 tok/s | 19.1 GB |
| 11 | Gemma 3n E4B IT (language-model-only export) 4-bit | 2.3 s | 62 tok/s | 6.4 GB | 2.3 s | 62 tok/s | 7.2 GB |
| 12 | Gemma 4 26B A4B IT 4-bit | 2.3 s | 76 tok/s | 17.8 GB | 1.8 s | 76 tok/s | 18.1 GB |
| 13 | Granite 4.1 8B 4-bit | 3.5 s | 45 tok/s | 6.8 GB | 3.5 s | 45 tok/s | 7.0 GB |
| 14 | Qwen 3.6 27B 4-bit | 11.3 s | 17 tok/s | 18.2 GB | 11.1 s | 17 tok/s | 19.1 GB |
| 15 | Qwen 3.8 27B 4-bit | 11.1 s | 17 tok/s | 18.3 GB | 11.0 s | 17 tok/s | 19.1 GB |

### Cohort m3-max-36gb-0205t2-mlx-20260909-r2

3 cells per model, 100 seconds between cells, an 8192-token window, mlx-serve 0.1 on macOS 26.6, measured 9 September 2026. Signed receipt `cc8f33b3cadd266c75e05c7e0a189694cda36e0e1bf60d95c5016c1a0112e684`.

| Cell | Model | Cold: first word | Cold: generation | Cold: peak memory | Warm: first word | Warm: generation | Warm: peak memory |
| ---: | --- | ---: | ---: | ---: | ---: | ---: | ---: |
| 1 | Gemma 3 12B IT (language-model-only export) 4-bit | 5.2 s | 34 tok/s | 10.4 GB | 5.1 s | 34 tok/s | 10.4 GB |
| 2 | Gemma 3n E4B IT (language-model-only export) 4-bit | 2.3 s | 61 tok/s | 6.4 GB | 2.3 s | 61 tok/s | 7.2 GB |
| 3 | Gemma 3 12B IT (language-model-only export) 4-bit | 5.1 s | 34 tok/s | 10.4 GB | 5.1 s | 34 tok/s | 10.3 GB |
| 4 | Gemma 3n E4B IT (language-model-only export) 4-bit | 2.3 s | 62 tok/s | 6.4 GB | 2.3 s | 63 tok/s | 7.2 GB |
| 5 | Gemma 3 12B IT (language-model-only export) 4-bit | 5.2 s | 34 tok/s | 10.4 GB | 5.2 s | 34 tok/s | 10.4 GB |
| 6 | Gemma 3n E4B IT (language-model-only export) 4-bit | 2.3 s | 61 tok/s | 6.4 GB | 2.3 s | 61 tok/s | 7.2 GB |

## The agency baseline, probe by probe

The baseline is three fixed documents in a small vault, each expanded from sources through Flow's own loop with its read and search tools, with the draft returned the way Flow asks for it. A model passes only when all three come back **composed**. A probe is **declined** when the model answered without a draft, and **unreadable** when the reply was not in the form Flow asks for; the receipt's own words for the cause are kept beside the verdict. Turns are round trips through the loop; calls are the lookups the model asked for on the way. The probe set is `flow-agency-v2.probes-1`.

- **Table note**: a short note with a three-row table in the middle of its prose; the draft has to grow the prose and leave the table intact.
- **First run**: three paragraphs of beekeeping notes with their spelling mistakes left in; the draft has to expand them without inventing what the notes do not say.
- **Expand topic**: one paragraph about an orchard's year, with the yield figures in a separate document beside it, so the draft has to find them and use them.

| Run | Model | Helper | Table note | First run | Expand topic | Result | Receipt |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 9 September 2026, 05:31 UTC | Qwen 3.6 27B 4-bit | mlx-serve `5c2d4d44` | Composed in 54.2 s (3 turns, 4 calls) | Composed in 57.3 s (3 turns, 3 calls) | Composed in 34.1 s (3 turns, 2 calls) | **Passes** (3 of 3) | `2979d7433d86` |
| 9 September 2026, 07:13 UTC | Gemma 3n E4B IT (language-model-only export) 4-bit | mlx-serve `5c2d4d44` | Unreadable in 9.4 s: the reply asked for lookups and answered at the same time | Unreadable in 7.3 s: the reply was not in the form Flow asks for | Unreadable in 5.5 s: the reply asked for lookups and answered at the same time | Does not pass (0 of 3) | `8815f72203d3` |
| 9 September 2026, 07:14 UTC | Granite 4.1 8B 4-bit | mlx-serve `5c2d4d44` | Composed in 11.3 s (2 turns, 2 calls) | Declined in 19.6 s: no draft came back between the markers | Declined in 7.8 s: no draft came back between the markers | Does not pass (1 of 3) | `d867f7ebe46e` |
| 9 September 2026, 07:14 UTC | Gemma 4 26B A4B IT 4-bit | mlx-serve `5c2d4d44` | Unreadable in 8.6 s: the reply was not in the form Flow asks for | Unreadable in 7.1 s: the reply was not in the form Flow asks for | Unreadable in 3.7 s: the reply was not in the form Flow asks for | Does not pass (0 of 3) | `671647f590fa` |
| 9 September 2026, 07:15 UTC | Qwen 3.8 27B 4-bit | mlx-serve `5c2d4d44` | Composed in 40.1 s (3 turns, 2 calls) | Composed in 45.4 s (3 turns, 3 calls) | Composed in 30.1 s (3 turns, 3 calls) | **Passes** (3 of 3) | `906b677b6614` |
| 9 September 2026, 08:46 UTC | Gemma 4 26B A4B IT 4-bit | mlx-serve `5c2d4d44` | Composed in 10.8 s (2 turns, 1 call) | Composed in 7.1 s (2 turns, 1 call) | Composed in 3.5 s (2 turns, 1 call) | **Passes** (3 of 3) | `a7ddcbeac85f` |
| 9 September 2026, 08:46 UTC | Gemma 3n E4B IT (language-model-only export) 4-bit | mlx-serve `5c2d4d44` | Declined in 8.9 s: no draft came back between the markers | Unreadable in 7.4 s: the reply was not in the form Flow asks for | Declined in 5.5 s: no draft came back between the markers | Does not pass (0 of 3) | `85f68b357158` |
| 9 September 2026, 09:02 UTC | Gemma 3 12B IT (language-model-only export) 4-bit | mlx-serve `5c2d4d44` | Unreadable in 5.1 s: the reply was not in the form Flow asks for | Composed in 14.1 s (2 turns, 2 calls) | Composed in 11.6 s (2 turns, 3 calls) | Does not pass (2 of 3) | `5efaff4ae231` |
| 9 September 2026, 17:16 UTC | Gemma 4 26B A4B IT 4-bit | mlx-serve `8e28b673` | Composed in 24.6 s (2 turns, 1 call) | Composed in 19.7 s (2 turns, 1 call) | Composed in 7.2 s (2 turns, 1 call) | **Passes** (3 of 3) | `221b2ca9772c` |

A model appears more than once when it was run more than once; every run is kept, in the order it happened, and the best run is what [[Models Flow Recommends]] reports.

## Task-specific small models

**Not yet measured.** A small model built for one task, such as finding names and numbers to redact or telling which language a passage is in, will be measured against what macOS already does and against the general model above before any is named here. Until then this section says so rather than guessing.

## How this page is made

This page is generated from the accepted lists, the signed cohort receipts and the agency-check receipts, in one pass, and it is regenerated whenever those change. If a number here and a number on [[Models Flow Recommends]] ever differed, that would be a defect in Flow, not a matter of opinion. Your edits to this document are safe: Flow offers you an update rather than overwriting it.
