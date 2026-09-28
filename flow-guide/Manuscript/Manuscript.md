---
title: Manuscript
category: personal-money
summary: "Bring a Word manuscript in, proofread it chapter by chapter, and publish the book with its cover."
tags: ["manuscript", "example"]
jobs:
  - kind: gather
    definition: Manuscript Refresh.md
    as: review
  - kind: keep-sources-fresh
    watch: ["Chapter Plan.md", chapters]
  - kind: reconcile-against-folder
    folder: chapters
---
# Manuscript

**The Estuary · a fictional novel in progress.** The Word manuscript was imported one chapter per file into `chapters/`, where each can be proofread on its own.

## Still being drafted

<!-- data: data/review-*.json#drafting -->
| Chapter | Title | Words |
| --- | --- | --- |
| C03 | The ferryman's ledger | 2,150 |

## The book so far

<!-- data: data/review-*.json#chapters -->
| Chapter | Title | Status | Words |
| --- | --- | --- | --- |
| C01 | The house on the estuary | Proofread | 4,210 |
| C02 | Low water | Proofread | 3,880 |
| C03 | The ferryman's ledger | Drafting | 2,150 |

## Review notes

<!-- night: notes -->
<!-- /night: notes -->
