# Curated Model Comparisons

These recommendation-ranked cards pair source-dated parent-model facts with Orionfold measurements from exact local artifacts in **Flow Runtime**. **Cold** is the first run after model load; **Warm** is a repeat with the model already loaded. Each number belongs to the named hardware envelope and working-set budget; it is not the source-admission order. These are bundled evidence, not local benchmark results from this Flow installation.

**Content date:** 2026-08-25

**Curator:** Orionfold

## MacBook Pro · Apple M3 Max · 36 GB

- **Hardware class:** `Mac15,10`; 30 GPU, 10 performance, and 4 efficiency cores
- **Recommendation:** Orionfold; 32 GB working set; 2026-08-25
- **Campaign 1 · 2026-08-25:** mlx-serve 0.1; macOS 26.6; 8192 tokens; cold then warm; 3 cells per artifact; 100 seconds between cells
- **Campaign 2 · 2026-08-25:** mlx-serve 0.1; macOS 26.6; 8192 tokens; cold then warm; 3 cells per artifact; 100 seconds between cells

### #1 Qwen 3.5 35B A3B 4-bit

**35B total / 3B active MoE** · 20.4 GB on disk

`Agents` `Instruct` `Reasoning` `Long Tasks` `Coding` `Vision`

Declared maximum **262144** tokens · served **8192** · actual prompt **1726–1728** tokens.

| Regime | N | First word | Input | Generation |
| --- | ---: | ---: | ---: | ---: |
| Cold | 3 | 7.4 s | 530 tok/s | 85 tok/s |
| Warm | 3 | 1.7 s | 998 tok/s | 86 tok/s |

| Regime | Peak memory | CPU | GPU (whole Mac) | Heat |
| --- | ---: | ---: | ---: | --- |
| Cold | 20.2 GB | 93.4% | 74.5% | Cool |
| Warm | 20.6 GB | 43.9% | 96.5% | Cool |

CPU follows Activity Monitor (100% = one core). GPU is whole-Mac utilization because macOS provides no public per-process GPU counter.

[Model config](https://huggingface.co/Qwen/Qwen3.5-35B-A3B/blob/59d61f3ce65a6d9863b86d2e96597125219dc754/README.md) · [LMArena \#149](https://huggingface.co/datasets/lmarena-ai/leaderboard-dataset) · [MLX artifact](https://huggingface.co/mlx-community/Qwen3.5-35B-A3B-4bit/tree/1e20fd8d42056f870933bf98ca6211024744f7ec) · 2026-08-25

### #2 Gemma 4 26B A4B IT 6-bit

**26B total / 4B active MoE** · 21.7 GB on disk

`Agents` `Instruct` `Reasoning` `Long Tasks` `Coding` `Vision`

Declared maximum **262144** tokens · served **8192** · actual prompt **1743–1746** tokens.

| Regime | N | First word | Input | Generation |
| --- | ---: | ---: | ---: | ---: |
| Cold | 3 | 8.2 s | 463 tok/s | 59 tok/s |
| Warm | 3 | 2.0 s | 900 tok/s | 59 tok/s |

[Model config](https://huggingface.co/google/gemma-4-26B-A4B-it/blob/4d7ae4984b7db7de8f8457170b3f1a419ee76d52/README.md) · [LMArena \#84](https://huggingface.co/datasets/lmarena-ai/leaderboard-dataset) · [MLX artifact](https://huggingface.co/mlx-community/gemma-4-26b-a4b-it-6bit/tree/968a9faa4b69230f3fc316b5755cb937a29c7ddc) · 2026-08-25

### #3 Qwen 3.8 27B 4-bit

**27B dense** · 16.1 GB on disk

`Agents` `Instruct` `Reasoning` `Long Tasks` `Coding` `Vision`

Declared maximum **262144** tokens · served **8192** · actual prompt **1726–1728** tokens.

| Regime | N | First word | Input | Generation |
| --- | ---: | ---: | ---: | ---: |
| Cold | 3 | 14.0 s | 156 tok/s | 17 tok/s |
| Warm | 3 | 11.1 s | 157 tok/s | 17 tok/s |

[Model config](https://huggingface.co/Qwen/Qwen3.8-27B/blob/1d4bf0f2ff6012fd82039f2fa52739d0dd7c60c0/README.md) · [LMArena \#81](https://huggingface.co/datasets/lmarena-ai/leaderboard-dataset) · [MLX artifact](https://huggingface.co/mlx-community/Qwen3.8-27B-4bit/tree/3e6447f082e89cc7f0bc6e5441afd38dfce760ff) · 2026-08-25

### #4 Gemma 4 31B IT 4-bit

**31B dense** · 18.4 GB on disk

`Agents` `Instruct` `Reasoning` `Long Tasks` `Coding` `Vision`

Declared maximum **262144** tokens · served **8192** · actual prompt **1743–1746** tokens.

| Regime | N | First word | Input | Generation |
| --- | ---: | ---: | ---: | ---: |
| Cold | 3 | 16.8 s | 131 tok/s | 14 tok/s |
| Warm | 3 | 13.4 s | 130 tok/s | 14 tok/s |

[Model config](https://huggingface.co/google/gemma-4-31B-it/blob/842da3794eaa0b77d5f08bae87a17459d91ff475/README.md) · [LMArena \#62](https://huggingface.co/datasets/lmarena-ai/leaderboard-dataset) · [MLX artifact](https://huggingface.co/mlx-community/gemma-4-31b-it-4bit/tree/696d436c404745a59f30e4939a658162b0a9e57f) · 2026-08-25

### #5 Muse Glimmer 30B 4-bit

**30B dense** · 19.4 GB on disk

`Agents` `Instruct` `Reasoning` `Long Tasks` `Coding` `Vision`

Declared maximum **131072** tokens · served **8192** · actual prompt **1768–1770** tokens.

| Regime | N | First word | Input | Generation |
| --- | ---: | ---: | ---: | ---: |
| Cold | 3 | 15.6 s | 148 tok/s | 16 tok/s |
| Warm | 3 | 14.0 s | 127 tok/s | 16 tok/s |

| Regime | Peak memory | CPU | GPU (whole Mac) | Heat |
| --- | ---: | ---: | ---: | --- |
| Cold | 20.5 GB | 31.1% | 100.0% | Cool |
| Warm | 20.4 GB | 30.5% | 100.0% | Cool |

CPU follows Activity Monitor (100% = one core). GPU is whole-Mac utilization because macOS provides no public per-process GPU counter.

[Model config](https://huggingface.co/meta-models/Muse-Glimmer-30B/blob/a4e59da52a7bc87ae7251dd5545c0dd437c44b68/README.md) · [LMArena \#101](https://huggingface.co/datasets/lmarena-ai/leaderboard-dataset) · [MLX artifact](https://huggingface.co/mlx-community/Muse-Glimmer-30B-4bit/tree/3e7677d7a40d348a3daba263a2b1c0aa41910710) · 2026-08-25

### #6 Qwen 3.5 27B 5-bit

**27B dense** · 19.4 GB on disk

`Agents` `Instruct` `Reasoning` `Long Tasks` `Coding` `Vision`

Declared maximum **262144** tokens · served **8192** · actual prompt **1726–1728** tokens.

| Regime | N | First word | Input | Generation |
| --- | ---: | ---: | ---: | ---: |
| Cold | 3 | 15.6 s | 146 tok/s | 14 tok/s |
| Warm | 3 | 11.5 s | 152 tok/s | 14 tok/s |

| Regime | Peak memory | CPU | GPU (whole Mac) | Heat |
| --- | ---: | ---: | ---: | --- |
| Cold | 20.1 GB | 27.7% | 100.0% | Cool |
| Warm | 20.8 GB | 11.5% | 100.0% | Cool |

CPU follows Activity Monitor (100% = one core). GPU is whole-Mac utilization because macOS provides no public per-process GPU counter.

[Model config](https://huggingface.co/Qwen/Qwen3.5-27B/blob/fc05daec18b0a78c049392ed2e771dde82bdf654/README.md) · [LMArena \#135](https://huggingface.co/datasets/lmarena-ai/leaderboard-dataset) · [MLX artifact](https://huggingface.co/mlx-community/Qwen3.5-27B-5bit/tree/8ec999add47e5a5bbc1a6f2c4e2b0497b81a461d) · 2026-08-25

---

Exact artifact, runtime, and receipt identities remain in Flow's verified signed bundle and are intentionally omitted from this reader-facing page.
