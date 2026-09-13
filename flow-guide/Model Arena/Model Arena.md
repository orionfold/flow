---
title: Model Arena
tags: [models, arena, measurements]
---
# Model Arena

**Choose for the work, then inspect the cost.** Published recommendations and measurements share the dated snapshot below. Speed is one measured property; it is not a quality score. Editing this personal copy changes its exhibits, not Flow's runtime recommendations.

## Published recommendations

These are the curator's authored choices for the stated memory envelope and date, after Flow's quality and resource gates. They are not live recommendations recomputed from these charts.

<!-- data: data/arena.json#choices -->
| Shift | Model | As of | Scope |
| --- | --- | --- | --- |
| Day | Gemma 4 E4B IT 4-bit | 2026-09-12 | MacBook Pro · Apple M3 Max · 36 GB |
| Night | Gemma 4 26B A4B IT 4-bit | 2026-09-12 | MacBook Pro · Apple M3 Max · 36 GB |

## Warm throughput leaderboard

This order compares median warm generation speed for exact local artifacts inside one named campaign. The conditions below identify its hardware, date and protocol. Day/Night selection markers refer to the published choices above.

<!-- data: data/arena.json#leaderboard -->
| Position | Model | Warm tokens per second | Day | Night |
| ---: | --- | ---: | --- | --- |
| 1 | Gemma 4 26B A4B IT 4-bit | 74.99 | — | Selected |
| 2 | Gemma 4 E4B IT 4-bit | 71.9 | Selected | — |
| 3 | Llama 3.1 8B Instruct 4-bit | 54.57 | — | — |

## Response and resource telemetry

Cold is the first request after model load; warm is its loaded repeat. Each bar is a median over the independent cold/warm pairs recorded in the conditions below; the telemetry rows retain their sample counts. First word is calculated from recorded timings; it is not a directly observed streaming latency.

```chart data: data/arena.json#metrics
chartType: Grouped Bar Chart
title: Generation speed after load and on repeat
subtitle: Tokens per second · higher is faster
source: data/arena.json, named public campaign
data:
  - {cpu_percent: 75.425, first_word_seconds: 6.806425, heat: "nominal", input_tokens_per_second: 532.85, model: "Gemma 4 26B A4B IT 4-bit", peak_memory_gib: 16.62, regime: "Cold", repository: "mlx-community/gemma-4-26b-a4b-it-4bit", revision: "0d77464eeb233a2da68ebf9d7dc4edaac7db956d", samples: 3, tokens_per_second: 74.226, whole_mac_gpu_percent: 77}
  - {cpu_percent: 23.887, first_word_seconds: 1.872175, heat: "nominal", input_tokens_per_second: 937.748, model: "Gemma 4 26B A4B IT 4-bit", peak_memory_gib: 16.88, regime: "Warm", repository: "mlx-community/gemma-4-26b-a4b-it-4bit", revision: "0d77464eeb233a2da68ebf9d7dc4edaac7db956d", samples: 3, tokens_per_second: 74.99, whole_mac_gpu_percent: 99}
  - {cpu_percent: 34.031, first_word_seconds: 2.723182, heat: "nominal", input_tokens_per_second: 1583.026, model: "Gemma 4 E4B IT 4-bit", peak_memory_gib: 5.84, regime: "Cold", repository: "mlx-community/gemma-4-e4b-it-4bit", revision: "475b9088d29754a3379866cf5aeb6b41acd313c2", samples: 3, tokens_per_second: 71.888, whole_mac_gpu_percent: 99}
  - {cpu_percent: 30.706, first_word_seconds: 1.080266, heat: "nominal", input_tokens_per_second: 1630.986, model: "Gemma 4 E4B IT 4-bit", peak_memory_gib: 6.15, regime: "Warm", repository: "mlx-community/gemma-4-e4b-it-4bit", revision: "475b9088d29754a3379866cf5aeb6b41acd313c2", samples: 3, tokens_per_second: 71.9, whole_mac_gpu_percent: 99}
  - {cpu_percent: 10.527, first_word_seconds: 3.673062, heat: "nominal", input_tokens_per_second: 614.562, model: "Llama 3.1 8B Instruct 4-bit", peak_memory_gib: 5.81, regime: "Cold", repository: "mlx-community/Llama-3.1-8B-Instruct-4bit", revision: "90215b22ec18e72f623dde2ea7af4097025160e2", samples: 3, tokens_per_second: 54.472, whole_mac_gpu_percent: 100}
  - {cpu_percent: 7.717, first_word_seconds: 2.853604, heat: "nominal", input_tokens_per_second: 617.202, model: "Llama 3.1 8B Instruct 4-bit", peak_memory_gib: 6.06, regime: "Warm", repository: "mlx-community/Llama-3.1-8B-Instruct-4bit", revision: "90215b22ec18e72f623dde2ea7af4097025160e2", samples: 3, tokens_per_second: 54.57, whole_mac_gpu_percent: 100}
semantic_types: {model: Category, regime: Category, tokens_per_second: Quantity}
encodings:
  x: {field: model}
  y: {field: tokens_per_second}
  group: {field: regime}
```

```chart data: data/arena.json#metrics
chartType: Grouped Bar Chart
title: Calculated time to the first word
subtitle: Seconds · lower is quicker
source: data/arena.json, named public campaign
data:
  - {cpu_percent: 75.425, first_word_seconds: 6.806425, heat: "nominal", input_tokens_per_second: 532.85, model: "Gemma 4 26B A4B IT 4-bit", peak_memory_gib: 16.62, regime: "Cold", repository: "mlx-community/gemma-4-26b-a4b-it-4bit", revision: "0d77464eeb233a2da68ebf9d7dc4edaac7db956d", samples: 3, tokens_per_second: 74.226, whole_mac_gpu_percent: 77}
  - {cpu_percent: 23.887, first_word_seconds: 1.872175, heat: "nominal", input_tokens_per_second: 937.748, model: "Gemma 4 26B A4B IT 4-bit", peak_memory_gib: 16.88, regime: "Warm", repository: "mlx-community/gemma-4-26b-a4b-it-4bit", revision: "0d77464eeb233a2da68ebf9d7dc4edaac7db956d", samples: 3, tokens_per_second: 74.99, whole_mac_gpu_percent: 99}
  - {cpu_percent: 34.031, first_word_seconds: 2.723182, heat: "nominal", input_tokens_per_second: 1583.026, model: "Gemma 4 E4B IT 4-bit", peak_memory_gib: 5.84, regime: "Cold", repository: "mlx-community/gemma-4-e4b-it-4bit", revision: "475b9088d29754a3379866cf5aeb6b41acd313c2", samples: 3, tokens_per_second: 71.888, whole_mac_gpu_percent: 99}
  - {cpu_percent: 30.706, first_word_seconds: 1.080266, heat: "nominal", input_tokens_per_second: 1630.986, model: "Gemma 4 E4B IT 4-bit", peak_memory_gib: 6.15, regime: "Warm", repository: "mlx-community/gemma-4-e4b-it-4bit", revision: "475b9088d29754a3379866cf5aeb6b41acd313c2", samples: 3, tokens_per_second: 71.9, whole_mac_gpu_percent: 99}
  - {cpu_percent: 10.527, first_word_seconds: 3.673062, heat: "nominal", input_tokens_per_second: 614.562, model: "Llama 3.1 8B Instruct 4-bit", peak_memory_gib: 5.81, regime: "Cold", repository: "mlx-community/Llama-3.1-8B-Instruct-4bit", revision: "90215b22ec18e72f623dde2ea7af4097025160e2", samples: 3, tokens_per_second: 54.472, whole_mac_gpu_percent: 100}
  - {cpu_percent: 7.717, first_word_seconds: 2.853604, heat: "nominal", input_tokens_per_second: 617.202, model: "Llama 3.1 8B Instruct 4-bit", peak_memory_gib: 6.06, regime: "Warm", repository: "mlx-community/Llama-3.1-8B-Instruct-4bit", revision: "90215b22ec18e72f623dde2ea7af4097025160e2", samples: 3, tokens_per_second: 54.57, whole_mac_gpu_percent: 100}
semantic_types: {model: Category, regime: Category, first_word_seconds: Duration}
encodings:
  x: {field: model}
  y: {field: first_word_seconds}
  group: {field: regime}
```

<!-- data: data/arena.json#metrics -->
| Model | Regime | Samples | Peak memory GiB | CPU percent | Whole Mac GPU percent | Heat |
| --- | --- | ---: | ---: | ---: | ---: | --- |
| Gemma 4 26B A4B IT 4-bit | Cold | 3 | 16.62 | 75.425 | 77 | nominal |
| Gemma 4 26B A4B IT 4-bit | Warm | 3 | 16.88 | 23.887 | 99 | nominal |
| Gemma 4 E4B IT 4-bit | Cold | 3 | 5.84 | 34.031 | 99 | nominal |
| Gemma 4 E4B IT 4-bit | Warm | 3 | 6.15 | 30.706 | 99 | nominal |
| Llama 3.1 8B Instruct 4-bit | Cold | 3 | 5.81 | 10.527 | 100 | nominal |
| Llama 3.1 8B Instruct 4-bit | Warm | 3 | 6.06 | 7.717 | 100 | nominal |

Memory is the sampled peak helper footprint, rounded to 0.01 GiB for display, not a general device-memory requirement. The public corpus retains the original byte values. CPU follows Activity Monitor: 100% = one core. GPU is utilization of the whole Mac, not this helper alone. Missing measurements stay blank; they are never zero.

## Quality and eligibility

Baseline completion checks whether a model can perform Flow's fixed tasks; it does not rank prose quality. The exact sources and accepted job comparisons behind selection remain in [[Model Recommendations]] and [[Model Evidence]]. Historical campaigns and primary model sources remain in [[Model Comparisons]].

<!-- data: data/arena.json#leaderboard -->
| Model | Day baseline | Night baseline | Quality source |
| --- | --- | --- | --- |
| Gemma 4 26B A4B IT 4-bit | Not recorded here | 8/8 | LMArena lmarena-ai/leaderboard-dataset text_style_control/latest, published 2026-09-02 |
| Gemma 4 E4B IT 4-bit | 8/8 | 3/8 | Flow job comparison e4b-over-llama-day-20260912; no direct Arena rank |
| Llama 3.1 8B Instruct 4-bit | 8/8 | 1/3 | LMArena lmarena-ai/leaderboard-dataset text_style_control/latest, published 2026-09-02 |

## Measurement conditions

<!-- data: data/arena.json#conditions -->
| Condition | Value |
| --- | --- |
| Campaign | m3-max-36gb-e4b-controls-mlx-20260912-r2 |
| Completed | 2026-09-12T07:48:06.189Z |
| Hardware | MacBook Pro · Apple M3 Max · 36 GB |
| Hardware identifier | Mac15,10 |
| GPU / performance / efficiency cores | 30 / 10 / 4 |
| Runtime | mlx-serve 0.2 |
| System | macOS 26.6 |
| Served context | 8192 tokens |
| Cold/warm pairs per model | 3 |
| Between pairs | 100 seconds |
| Telemetry interval | 1000 ms |
| Evidence assembled | 2026-09-12 |
| Curator | Orionfold |

This is the named curator's public evidence, not a benchmark of this Flow installation. Earlier campaigns retain their own conditions and must not be pooled with these bars.

## Make this workspace yours

Copy the whole **Model Arena** folder, add the copy to Flow, then open this document. Start by editing a chart's title in the chart editor: the title changes while the measured values stay fixed in `data/arena.json`. After replacing that file with another complete export from the verified public corpus, choose **Settings ▸ Night Shift ▸ Run now** to refresh this document's bound recommendations, conditions, tables and charts together. Scheduling can stay off for a manual refresh. Keep the campaign and choice metadata with its measurement rows; changing a metric or position by hand creates your own analysis, not a new curator recommendation. It does not measure a model or alter Flow's recommendations. Keep your own experiments in separate, clearly labelled source files, with their hardware, dates and conditions.

The four supporting model pages and their public assets travel with the folder. No account, network read or paid model is needed to inspect or redraw this snapshot.
