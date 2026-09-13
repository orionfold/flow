---
title: Supplier Review
tags: [procurement, operations, living-workspace, fictional-example]
jobs:
  - kind: gather
    definition: Supplier Review Refresh.md
    into: data
    as: supplier-review
  - kind: keep-sources-fresh
    watch: [Supplier Review Settings.md, inputs, sources]
---
# Supplier Review

Linden Workshop has three renewals to prepare. The brief separates what has been offered from what has been spent, and puts unresolved service terms next to the prices. A lower proposed fee is an option to investigate, not a realized saving.

> **Fictional commercial review.** USD throughout. No supplier has been selected, no contract changed, and no order sent.

<!-- data: data/supplier-review-*.json#review -->
| Business | As of | Spend period |
| --- | --- | --- |
| Linden Workshop | 2026-09-12 | March–August 2026 |

## See the movement within each relationship

Each pair compares a supplier's current and offered **annual fixed service fee**. The three suppliers provide different services; position on the chart is not a supplier ranking.

```chart data: data/supplier-review-*.json#quoteDots
chartType: Ranged Dot Plot
title: "Current and offered annual fixed fees"
subtitle: "USD per twelve-month term · connect each supplier to its own baseline"
source: "Newest local quotation snapshot; SR-01 through SR-03"
data:
  - {supplier: "Grove Packaging", basis: "Offered fee", annual: 12600}
  - {supplier: "Grove Packaging", basis: "Current fee", annual: 12000}
  - {supplier: "Lane Freight", basis: "Offered fee", annual: 17280}
  - {supplier: "Lane Freight", basis: "Current fee", annual: 18000}
  - {supplier: "Paper Harbor", basis: "Offered fee", annual: 16200}
  - {supplier: "Paper Harbor", basis: "Current fee", annual: 18000}
semantic_types: {"supplier": "Name", "basis": "Category", "annual": "Amount"}
encodings:
  y: {"field": "supplier"}
  x: {"field": "annual"}
  color: {"field": "basis", "scheme": "purples"}
```

<!-- data: data/supplier-review-*.json#comparison -->
| Supplier | Current | Offered | Change | Change pct | Renewal |
| --- | --- | --- | --- | --- | --- |
| Paper Harbor | 18000 | 16200 | -1800 | -10 | 2026-10-01 |
| Grove Packaging | 12000 | 12600 | 600 | 5 | 2026-11-01 |
| Lane Freight | 18000 | 17280 | -720 | -4 | 2026-12-01 |

## The price question is only half the review

| Relationship | What to establish before deciding | Owner |
| --- | --- | --- |
| Paper Harbor | Does the revised offer preserve the required production turnaround? | Print operations |
| Grove Packaging | What work explains the higher fixed fee? | Packaging lead |
| Lane Freight | What response commitment applies when a delivery needs escalation? | Dispatch lead |

These are open questions from the **12 September sample packet**. [[Supplier Review Sources]] links the quotations and explains the one changed offer.

## Variable purchases are a different measure

These are actuals within the fictional six-month register, excluding fixed fees. They are not annualized and do not predict the next term.

<!-- data: data/supplier-review-*.json#spend -->
| Supplier | Spent |
| --- | --- |
| Lane Freight | 11700 |
| Paper Harbor | 8100 |
| Grove Packaging | 5500 |

<!-- data: data/supplier-review-*.json#summary -->
| Metric | Value |
| --- | --- |
| Current annual fixed fees | 48000 |
| Offered annual fixed fees | 46080 |
| Change in fixed fees | -1920 |
| Six-month variable purchases | 25300 |

## Make it yours

1. Copy this entire **Supplier Review** folder into your own workspace and add the copy to Flow. Keep quotes, settings, snapshots, and captures together.
2. Open [[supplier-snapshot-2026-09-12]] and use the **Suppliers** table's **Open in the table editor** control. Change Paper Harbor's `offered` amount from **16200 to 16500**, then save. Use **Run now** from the moon.
3. Expect its offered dot and table value to become **16500**, its fee change to become **−1500**, and the offered-fee total to become **46380**. The six-month variable-purchase total stays **25300**.
4. Replace the sample suppliers and source notes with your own records. Preserve consistent currencies and term lengths; put absent quotations in a pending note rather than entering a made-up zero. Replace both dated examples when their history is no longer useful.
5. Open [[Supplier Review Settings]] for the input conventions. To inspect calculations, open [[Supplier Review Refresh]], then choose **File ▸ Edit Definition…**. Return here and use **File ▸ Night Shift Jobs…** to configure source watches; turn on Night Shift if you want scheduled runs.

## Optional overnight notes

The saved jobs collect local data and watch source changes. They do not need a model. To add a short interpretation, use **File ▸ Night Shift Jobs…** on this document and add **Overnight notes** after configuring a local Night model. Read the proposed notes against the inputs; an interpretation is not another source. Nothing is sent or published by this workspace.

<!-- night: notes -->
<!-- /night: notes -->
