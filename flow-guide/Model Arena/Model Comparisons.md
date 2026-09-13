# Model Comparisons

These cards pair source-dated parent-model facts with Orionfold measurements from exact local artifacts in **Flow Runtime**. **Cold** is the first run after model load; **Warm** is a repeat with the model already loaded. Historical comparison numbers preserve Orionfold’s dated ordering for the named hardware envelope and working-set budget. These are bundled evidence, not local benchmark results from this Flow installation.

For Flow’s current Day and Night choices for each Mac memory tier, see [[Model Recommendations]].

**Content date:** 2026-09-12

**Curator:** Orionfold

## MacBook Pro · Apple M3 Max · 36 GB

- **Hardware class:** `Mac15,10`; 30 GPU, 10 performance, and 4 efficiency cores
- **Historical comparison order:** Orionfold; 32 GB working set; 2026-08-25
- **Campaign 1 · 2026-09-12:** mlx-serve 0.2; macOS 26.6; 8192 tokens; cold then warm; 3 cells per artifact; 100 seconds between cells
- **Campaign 2 · 2026-08-25:** mlx-serve 0.1; macOS 26.6; 8192 tokens; cold then warm; 3 cells per artifact; 100 seconds between cells
- **Campaign 3 · 2026-08-25:** mlx-serve 0.1; macOS 26.6; 8192 tokens; cold then warm; 3 cells per artifact; 100 seconds between cells

### Historical #1 Qwen 3.5 35B A3B 4-bit

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

### Historical #2 Gemma 4 26B A4B IT 6-bit

**26B total / 4B active MoE** · 21.7 GB on disk

`Agents` `Instruct` `Reasoning` `Long Tasks` `Coding` `Vision`

Declared maximum **262144** tokens · served **8192** · actual prompt **1743–1746** tokens.

| Regime | N | First word | Input | Generation |
| --- | ---: | ---: | ---: | ---: |
| Cold | 3 | 8.2 s | 463 tok/s | 59 tok/s |
| Warm | 3 | 2.0 s | 900 tok/s | 59 tok/s |

[Model config](https://huggingface.co/google/gemma-4-26B-A4B-it/blob/4d7ae4984b7db7de8f8457170b3f1a419ee76d52/README.md) · [LMArena \#84](https://huggingface.co/datasets/lmarena-ai/leaderboard-dataset) · [MLX artifact](https://huggingface.co/mlx-community/gemma-4-26b-a4b-it-6bit/tree/968a9faa4b69230f3fc316b5755cb937a29c7ddc) · 2026-08-25

### Historical #3 Qwen 3.8 27B 4-bit

**27B dense** · 16.1 GB on disk

`Agents` `Instruct` `Reasoning` `Long Tasks` `Coding` `Vision`

Declared maximum **262144** tokens · served **8192** · actual prompt **1726–1728** tokens.

| Regime | N | First word | Input | Generation |
| --- | ---: | ---: | ---: | ---: |
| Cold | 3 | 14.0 s | 156 tok/s | 17 tok/s |
| Warm | 3 | 11.1 s | 157 tok/s | 17 tok/s |

[Model config](https://huggingface.co/Qwen/Qwen3.8-27B/blob/1d4bf0f2ff6012fd82039f2fa52739d0dd7c60c0/README.md) · [LMArena \#81](https://huggingface.co/datasets/lmarena-ai/leaderboard-dataset) · [MLX artifact](https://huggingface.co/mlx-community/Qwen3.8-27B-4bit/tree/3e6447f082e89cc7f0bc6e5441afd38dfce760ff) · 2026-08-25

### Historical #4 Gemma 4 31B IT 4-bit

**31B dense** · 18.4 GB on disk

`Agents` `Instruct` `Reasoning` `Long Tasks` `Coding` `Vision`

Declared maximum **262144** tokens · served **8192** · actual prompt **1743–1746** tokens.

| Regime | N | First word | Input | Generation |
| --- | ---: | ---: | ---: | ---: |
| Cold | 3 | 16.8 s | 131 tok/s | 14 tok/s |
| Warm | 3 | 13.4 s | 130 tok/s | 14 tok/s |

[Model config](https://huggingface.co/google/gemma-4-31B-it/blob/842da3794eaa0b77d5f08bae87a17459d91ff475/README.md) · [LMArena \#62](https://huggingface.co/datasets/lmarena-ai/leaderboard-dataset) · [MLX artifact](https://huggingface.co/mlx-community/gemma-4-31b-it-4bit/tree/696d436c404745a59f30e4939a658162b0a9e57f) · 2026-08-25

### Historical #5 Muse Glimmer 30B 4-bit

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

### Historical #6 Qwen 3.5 27B 5-bit

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

### Measured · Gemma 4 E4B IT 4-bit

**8B dense with per-layer embeddings / 4.5B effective** · 5.2 GB on disk

`Text` `Instruct` `Reasoning` `Coding`

Declared maximum **131072** tokens · served **8192** · actual prompt **1739–1742** tokens.

| Regime | N | First word | Input | Generation |
| --- | ---: | ---: | ---: | ---: |
| Cold | 3 | 2.7 s | 1583 tok/s | 72 tok/s |
| Warm | 3 | 1.1 s | 1631 tok/s | 72 tok/s |

| Regime | Peak memory | CPU | GPU (whole Mac) | Heat |
| --- | ---: | ---: | ---: | --- |
| Cold | 5.8 GB | 34.0% | 99.0% | Cool |
| Warm | 6.1 GB | 30.7% | 99.0% | Cool |

CPU follows Activity Monitor (100% = one core). GPU is whole-Mac utilization because macOS provides no public per-process GPU counter.

[Model config](https://huggingface.co/google/gemma-4-E4B-it/blob/fee6332c1abaafb77f6f9624236c63aa2f1d0187/README.md) · [Pinned Google Gemma 4 E4B model card \(publisher benchmarks\)](https://huggingface.co/google/gemma-4-E4B-it/blob/fee6332c1abaafb77f6f9624236c63aa2f1d0187/README.md) · [MLX artifact](https://huggingface.co/mlx-community/gemma-4-e4b-it-4bit/tree/475b9088d29754a3379866cf5aeb6b41acd313c2) · 2026-09-12

### Measured · Llama 3.1 8B Instruct 4-bit

**8B dense** · 4.5 GB on disk

`Text` `Instruct` `Agents` `Coding` `Long Tasks`

Declared maximum **131072** tokens · served **8192** · actual prompt **1750–1752** tokens.

| Regime | N | First word | Input | Generation |
| --- | ---: | ---: | ---: | ---: |
| Cold | 3 | 3.7 s | 615 tok/s | 54 tok/s |
| Warm | 3 | 2.9 s | 617 tok/s | 55 tok/s |

| Regime | Peak memory | CPU | GPU (whole Mac) | Heat |
| --- | ---: | ---: | ---: | --- |
| Cold | 5.8 GB | 10.5% | 100.0% | Cool |
| Warm | 6.1 GB | 7.7% | 100.0% | Cool |

CPU follows Activity Monitor (100% = one core). GPU is whole-Mac utilization because macOS provides no public per-process GPU counter.

[Model config](https://huggingface.co/meta-llama/Llama-3.1-8B-Instruct/blob/0e9e39f249a16976918f6564b8830bc894c89659/README.md) · [LMArena \#326](https://huggingface.co/datasets/lmarena-ai/leaderboard-dataset) · [MLX artifact](https://huggingface.co/mlx-community/Llama-3.1-8B-Instruct-4bit/tree/90215b22ec18e72f623dde2ea7af4097025160e2) · 2026-09-08

### Measured · Gemma 4 26B A4B IT 4-bit

**26B total / 4B active MoE** · 15.4 GB on disk

`Agents` `Instruct` `Reasoning` `Long Tasks` `Coding` `Vision`

Declared maximum **262144** tokens · served **8192** · actual prompt **1743–1746** tokens.

| Regime | N | First word | Input | Generation |
| --- | ---: | ---: | ---: | ---: |
| Cold | 3 | 6.8 s | 533 tok/s | 74 tok/s |
| Warm | 3 | 1.9 s | 938 tok/s | 75 tok/s |

| Regime | Peak memory | CPU | GPU (whole Mac) | Heat |
| --- | ---: | ---: | ---: | --- |
| Cold | 16.6 GB | 75.4% | 77.0% | Cool |
| Warm | 16.9 GB | 23.9% | 99.0% | Cool |

CPU follows Activity Monitor (100% = one core). GPU is whole-Mac utilization because macOS provides no public per-process GPU counter.

[Model config](https://huggingface.co/google/gemma-4-26B-A4B-it/blob/4d7ae4984b7db7de8f8457170b3f1a419ee76d52/README.md) · [LMArena \#85](https://huggingface.co/datasets/lmarena-ai/leaderboard-dataset) · [MLX artifact](https://huggingface.co/mlx-community/gemma-4-26b-a4b-it-4bit/tree/0d77464eeb233a2da68ebf9d7dc4edaac7db956d) · 2026-09-08

---

Exact artifact, runtime, and receipt identities remain in Flow's verified signed bundle and are intentionally omitted from this reader-facing page.
