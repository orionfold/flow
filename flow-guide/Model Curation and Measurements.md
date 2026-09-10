---
title: Model Curation and Measurements
tags: [flow, models, agency, evidence]
researched: 2026-09-09
curator: Orionfold
---

# Model Curation and Measurements

This is the evidence behind [[Models Flow Recommends]], shown whole. That page keeps one outcome per model; this one keeps every list row, every measurement cell and every agency-check run with its three probes named and judged, each number beside the receipt it came from. Both pages are generated from the same files on the same date, so they cannot disagree.

Everything measured here was run on a 36 GB MacBook Pro with an Apple M3 Max (Mac15,10), through Flow Runtime, with the receipts signed by Orionfold. The numbers are that Mac's, not yours. The evidence was last assembled on 9 September 2026.

## How a model gets onto a list

Flow keeps two lists, one per class. A model is admitted by quality rank first, then by whether it can fit the class's share of memory and its download ceiling, then by whether Flow Runtime can load its files at all. Nothing on a list is a recommendation yet: a row becomes a pick only after it is measured and passes the agency baseline below.

### The day list (accepted 8 September 2026)

Quality ranks are from LMArena lmarena-ai/leaderboard-dataset text_style_control/latest, published 2026-09-02. To fit this class on the measured Mac a model's working set may take a third of memory, 12 GB here, its download may be at most 8.6 GB, and one model is loaded at a time. Flow Runtime's loaders were read from ml-explore/mlx-swift-lm at d7dc03d8, inspected 2026-09-08.

| # | Model | Download | Quality rank | Working set (projected) | Flow Runtime |
| ---: | --- | ---: | ---: | ---: | --- |
| 1 | Gemma 3 12B IT (language-model-only export) 4-bit | 7.2 GB | #217 (gemma-3-12b-it) | 12.9 GB (10.6 GB with a sliding cache) | loads and runs |
| 2 | Gemma 3n E4B IT (language-model-only export) 4-bit | 3.9 GB | #249 (gemma-3n-e4b-it) | 7.0 GB (6.5 GB with a sliding cache) | loads and runs |
| 3 | Granite 4.1 8B 4-bit | 5.2 GB | #264 (granite-4.1-8b) | 9.1 GB | loads and runs |
| 4 | Gemma 3 4B IT (language-model-only export) 4-bit | 2.6 GB | #267 (gemma-3-4b-it) | 6.2 GB (5.4 GB with a sliding cache) | loads and runs |
| 5 | Gemma 2 9B IT 4-bit | 5.2 GB | #296 (gemma-2-9b-it) | 10.5 GB (9.4 GB with a sliding cache) | not yet run |
| 6 | Phi-4 4-bit | 8.3 GB | #303 (phi-4) | 12.4 GB | not yet run |
| 7 | Llama 3.1 8B Instruct 4-bit | 4.5 GB | #326 (llama-3.1-8b-instruct) | 8.1 GB | loads and runs |
| 8 | Gemma 2 2B IT 4-bit | 1.5 GB | #330 (gemma-2-2b-it) | 4.9 GB (4.5 GB with a sliding cache) | not yet run |
| 9 | Llama 3.2 3B Instruct 4-bit | 1.8 GB | #352 (llama-3.2-3b-instruct) | 5.3 GB | not yet run |
| 10 | Mistral 7B Instruct v0.2 4-bit | 4.3 GB | #361 (mistral-7b-instruct-v0.2) | 7.8 GB | loads and runs |

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

A cohort loads one model at a time and runs the same two requests against it: **cold**, the first request after the model loads, and **warm**, the same request again with the model already resident. First word is the time to the first token; generation is the tokens a second after it; peak memory is the most the helper held during the request. Each cohort is one signed receipt, and its digest is on the heading. 30 cells in all.

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

### Cohort m3-max-36gb-0205t3-mlx-20260909-r2

3 cells per model, 100 seconds between cells, an 8192-token window, mlx-serve 0.1 on macOS 26.6, measured 9 September 2026. Signed receipt `0012b886019826a5c9f3950a6fef938819c40983dbdc155bb37208d816ffccc4`.

| Cell | Model | Cold: first word | Cold: generation | Cold: peak memory | Warm: first word | Warm: generation | Warm: peak memory |
| ---: | --- | ---: | ---: | ---: | ---: | ---: | ---: |
| 1 | Gemma 3 4B IT (language-model-only export) 4-bit | 1.6 s | 91 tok/s | 4.5 GB | 1.6 s | 92 tok/s | 4.6 GB |
| 2 | Llama 3.1 8B Instruct 4-bit | 2.8 s | 55 tok/s | 6.2 GB | 2.8 s | 55 tok/s | 6.5 GB |
| 3 | Mistral 7B Instruct v0.2 4-bit | 2.8 s | 57 tok/s | 6.2 GB | 2.8 s | 57 tok/s | 6.4 GB |
| 4 | Gemma 3 4B IT (language-model-only export) 4-bit | 1.6 s | 91 tok/s | 4.5 GB | 1.6 s | 91 tok/s | 4.6 GB |
| 5 | Llama 3.1 8B Instruct 4-bit | 2.8 s | 55 tok/s | 6.2 GB | 2.8 s | 55 tok/s | 6.5 GB |
| 6 | Mistral 7B Instruct v0.2 4-bit | 2.8 s | 57 tok/s | 6.2 GB | 2.8 s | 57 tok/s | 6.4 GB |
| 7 | Gemma 3 4B IT (language-model-only export) 4-bit | 1.6 s | 91 tok/s | 4.5 GB | 1.6 s | 91 tok/s | 4.6 GB |
| 8 | Llama 3.1 8B Instruct 4-bit | 2.8 s | 55 tok/s | 6.2 GB | 2.8 s | 55 tok/s | 6.5 GB |
| 9 | Mistral 7B Instruct v0.2 4-bit | 2.8 s | 57 tok/s | 6.2 GB | 2.8 s | 57 tok/s | 6.4 GB |

## The agency baseline, probe by probe

The baseline is 8 fixed documents in a small vault, each expanded from sources through Flow's own loop with its read and search tools, with the draft returned the way Flow asks for it. A model passes only when every probe comes back **composed**. A probe is **declined** when the model answered without a draft, and **unreadable** when the reply was not in the form Flow asks for; the receipt's own words for the cause are kept beside the verdict. Turns are round trips through the loop; calls are the lookups the model asked for on the way. The envelope names the shape the model was handed: **two-phase** is the loop, where the model asks for its lookups and answers when it has enough; **one-turn** is the day's shape, where Flow does the lookups first and hands the model one request whose reply is the draft. The probe set in force is `flow-agency-v2.probes-2`; it grew from three probes to eight on 9 September 2026, the day a row first composed all three in one turn, and a one-turn run judged on the earlier set is shown on the probes it ran and earns no day pick, because a day pick needs the whole set in force; the night's picks were judged through the loop on the first three.

- **Table note**: a short note with a three-row table in the middle of its prose; the draft has to grow the prose and leave the table intact.
- **First run**: three paragraphs of beekeeping notes with their spelling mistakes left in; the draft has to expand them without inventing what the notes do not say.
- **Expand topic**: one paragraph about an orchard's year, with the yield figures in a separate document beside it, so the draft has to find them and use them.
- **Site actions**: four action items from a farm visit as a list, with the costs, names and dates in a brief beside it, so each item has to be grown from what the brief says.
- **Orchard in Spanish**: the orchard paragraph in Spanish, with its figures in a Spanish document beside it, so the draft has to stay in Spanish and find them there.
- **Tool readme**: a short readme with a fenced command line in it and the command's flags in a document beside it; the fence has to survive.
- **Travel plan**: a two-day plan with nothing beside it to find, so the draft has to grow it without inventing a fact.
- **Quarter review**: a longer review under three headings with its figures in a document beside it, so the draft has to keep the headings and place the figures.

| Run | Model | Helper | Envelope | Table note | First run | Expand topic | Site actions | Orchard in Spanish | Tool readme | Travel plan | Quarter review | Result | Receipt |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 9 September 2026, 05:31 UTC | Qwen 3.6 27B 4-bit | mlx-serve `5c2d4d44` | two-phase | Composed in 54.2 s (3 turns, 4 calls) | Composed in 57.3 s (3 turns, 3 calls) | Composed in 34.1 s (3 turns, 2 calls) | not run | not run | not run | not run | not run | **Passes** (3 of 3) | `2979d7433d86` |
| 9 September 2026, 07:13 UTC | Gemma 3n E4B IT (language-model-only export) 4-bit | mlx-serve `5c2d4d44` | two-phase | Unreadable in 9.4 s: the reply asked for lookups and answered at the same time | Unreadable in 7.3 s: the reply was not in the form Flow asks for | Unreadable in 5.5 s: the reply asked for lookups and answered at the same time | not run | not run | not run | not run | not run | Does not pass (0 of 3) | `8815f72203d3` |
| 9 September 2026, 07:14 UTC | Granite 4.1 8B 4-bit | mlx-serve `5c2d4d44` | two-phase | Composed in 11.3 s (2 turns, 2 calls) | Declined in 19.6 s: no draft came back between the markers | Declined in 7.8 s: no draft came back between the markers | not run | not run | not run | not run | not run | Does not pass (1 of 3) | `d867f7ebe46e` |
| 9 September 2026, 07:14 UTC | Gemma 4 26B A4B IT 4-bit | mlx-serve `5c2d4d44` | two-phase | Unreadable in 8.6 s: the reply was not in the form Flow asks for | Unreadable in 7.1 s: the reply was not in the form Flow asks for | Unreadable in 3.7 s: the reply was not in the form Flow asks for | not run | not run | not run | not run | not run | Does not pass (0 of 3) | `671647f590fa` |
| 9 September 2026, 07:15 UTC | Qwen 3.8 27B 4-bit | mlx-serve `5c2d4d44` | two-phase | Composed in 40.1 s (3 turns, 2 calls) | Composed in 45.4 s (3 turns, 3 calls) | Composed in 30.1 s (3 turns, 3 calls) | not run | not run | not run | not run | not run | **Passes** (3 of 3) | `906b677b6614` |
| 9 September 2026, 08:46 UTC | Gemma 4 26B A4B IT 4-bit | mlx-serve `5c2d4d44` | two-phase | Composed in 10.8 s (2 turns, 1 call) | Composed in 7.1 s (2 turns, 1 call) | Composed in 3.5 s (2 turns, 1 call) | not run | not run | not run | not run | not run | **Passes** (3 of 3) | `a7ddcbeac85f` |
| 9 September 2026, 08:46 UTC | Gemma 3n E4B IT (language-model-only export) 4-bit | mlx-serve `5c2d4d44` | two-phase | Declined in 8.9 s: no draft came back between the markers | Unreadable in 7.4 s: the reply was not in the form Flow asks for | Declined in 5.5 s: no draft came back between the markers | not run | not run | not run | not run | not run | Does not pass (0 of 3) | `85f68b357158` |
| 9 September 2026, 09:02 UTC | Gemma 3 12B IT (language-model-only export) 4-bit | mlx-serve `5c2d4d44` | two-phase | Unreadable in 5.1 s: the reply was not in the form Flow asks for | Composed in 14.1 s (2 turns, 2 calls) | Composed in 11.6 s (2 turns, 3 calls) | not run | not run | not run | not run | not run | Does not pass (2 of 3) | `5efaff4ae231` |
| 9 September 2026, 17:16 UTC | Gemma 4 26B A4B IT 4-bit | mlx-serve `8e28b673` | two-phase | Composed in 24.6 s (2 turns, 1 call) | Composed in 19.7 s (2 turns, 1 call) | Composed in 7.2 s (2 turns, 1 call) | not run | not run | not run | not run | not run | **Passes** (3 of 3) | `221b2ca9772c` |
| 9 September 2026, 20:11 UTC | Gemma 3 4B IT (language-model-only export) 4-bit | mlx-serve `8e28b673` | two-phase | Unreadable in 21.6 s: the reply asked for lookups and answered at the same time | Declined in 12.0 s: no draft came back between the markers | Unreadable in 8.7 s: the reply asked for lookups and answered at the same time | not run | not run | not run | not run | not run | Does not pass (0 of 3) | `10117317e769` |
| 9 September 2026, 20:12 UTC | Llama 3.1 8B Instruct 4-bit | mlx-serve `8e28b673` | two-phase | Unreadable in 7.9 s: the reply was empty | Unreadable in 3.3 s: the reply was empty | Composed in 3.4 s (2 turns, 1 call) | not run | not run | not run | not run | not run | Does not pass (1 of 3) | `3155ab553a4c` |
| 9 September 2026, 20:13 UTC | Mistral 7B Instruct v0.2 4-bit | mlx-serve `8e28b673` | two-phase | Unreadable in 4.1 s: the reply was not in the form Flow asks for | Unreadable in 2.5 s: the reply was not in the form Flow asks for | Unreadable in 2.5 s: the reply asked for lookups and answered at the same time | not run | not run | not run | not run | not run | Does not pass (0 of 3) | `bb74079a0d45` |
| 9 September 2026, 22:55 UTC | Llama 3.1 8B Instruct 4-bit | mlx-serve `8e28b673` | one-turn | Composed in 7.5 s (1 turn, 5 calls) | Composed in 7.7 s (1 turn, 5 calls) | Composed in 7.7 s (1 turn, 5 calls) | not run | not run | not run | not run | not run | **Passes** (3 of 3) | `d6ac271ef5a2` |
| 9 September 2026, 23:01 UTC | Llama 3.1 8B Instruct 4-bit | mlx-serve `8e28b673` | one-turn | Composed in 8.8 s (1 turn, 5 calls) | Composed in 7.7 s (1 turn, 5 calls) | Composed in 6.3 s (1 turn, 5 calls) | Composed in 7.8 s (1 turn, 5 calls) | Composed in 5.9 s (1 turn, 5 calls) | Composed in 5.2 s (1 turn, 5 calls) | Composed in 7.5 s (1 turn, 5 calls) | Composed in 6.9 s (1 turn, 5 calls) | **Passes** (8 of 8) | `c5d8607655e5` |
| 9 September 2026, 23:02 UTC | Gemma 3 4B IT (language-model-only export) 4-bit | mlx-serve `8e28b673` | one-turn | Composed in 8.7 s (1 turn, 5 calls) | Composed in 10.8 s (1 turn, 5 calls) | Composed in 13.7 s (1 turn, 5 calls) | Composed in 12.4 s (1 turn, 5 calls) | Composed in 20.6 s (1 turn, 5 calls) | Composed in 13.2 s (1 turn, 5 calls) | Composed in 9.4 s (1 turn, 5 calls) | Composed in 14.7 s (1 turn, 5 calls) | **Passes** (8 of 8) | `bf7a5f5f4c4a` |
| 9 September 2026, 23:04 UTC | Mistral 7B Instruct v0.2 4-bit | mlx-serve `8e28b673` | one-turn | Composed in 14.3 s (1 turn, 5 calls) | Composed in 7.4 s (1 turn, 5 calls) | Composed in 8.7 s (1 turn, 5 calls) | Composed in 10.9 s (1 turn, 5 calls) | Composed in 8.7 s (1 turn, 5 calls) | Composed in 10.4 s (1 turn, 5 calls) | Composed in 8.2 s (1 turn, 5 calls) | Composed in 12.8 s (1 turn, 5 calls) | **Passes** (8 of 8) | `0d171b9570f9` |
| 9 September 2026, 23:06 UTC | Gemma 3 12B IT (language-model-only export) 4-bit | mlx-serve `8e28b673` | one-turn | Declined in 34.5 s: no draft came back between the markers | Declined in 28.5 s: no draft came back between the markers | Composed in 21.6 s (1 turn, 5 calls) | Declined in 18.1 s: no draft came back between the markers | Declined in 13.6 s: no draft came back between the markers | Declined in 28.3 s: no draft came back between the markers | Declined in 17.9 s: no draft came back between the markers | Declined in 35.5 s: no draft came back between the markers | Does not pass (1 of 8) | `9110cefebc76` |
| 10 September 2026, 00:25 UTC | Gemma 4 26B A4B IT 4-bit | mlx-serve `8e28b673` | two-phase | Composed in 7.8 s (2 turns, 1 call) | Composed in 7.0 s (2 turns, 1 call) | Composed in 3.5 s (2 turns, 1 call) | Composed in 3.3 s (1 turn, 0 calls) | Composed in 6.0 s (2 turns, 1 call) | Composed in 5.0 s (2 turns, 1 call) | Declined in 6.4 s: no draft came back between the markers | Composed in 4.5 s (2 turns, 1 call) | Does not pass (7 of 8) | `c050f1294cf5` |
| 10 September 2026, 00:26 UTC | Qwen 3.8 27B 4-bit | mlx-serve `8e28b673` | two-phase | Composed in 37.6 s (3 turns, 2 calls) | Composed in 44.8 s (3 turns, 3 calls) | Composed in 27.0 s (3 turns, 3 calls) | Composed in 52.3 s (3 turns, 5 calls) | Composed in 50.2 s (3 turns, 3 calls) | Composed in 48.6 s (3 turns, 3 calls) | Composed in 76.3 s (3 turns, 2 calls) | Composed in 55.4 s (3 turns, 4 calls) | **Passes** (8 of 8) | `4948eb1e035e` |

A model appears more than once when it was run more than once; every run is kept, in the order it happened, and the best run is what [[Models Flow Recommends]] reports.

## Task-specific small models

**Not yet measured.** A small model built for one task, such as finding names and numbers to redact or telling which language a passage is in, will be measured against what macOS already does and against the general model above before any is named here. Until then this section says so rather than guessing.

## How this page is made

This page is generated from the accepted lists, the signed cohort receipts and the agency-check receipts, in one pass, and it is regenerated whenever those change. If a number here and a number on [[Models Flow Recommends]] ever differed, that would be a defect in Flow, not a matter of opinion. Your edits to this document are safe: Flow offers you an update rather than overwriting it.
