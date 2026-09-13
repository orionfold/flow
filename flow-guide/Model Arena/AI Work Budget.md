---
title: AI Work Budget
tags: ["model-arena", "example"]
---
# AI Work Budget

**Fictional budgeting example · separate from Model Arena’s measured evidence**

## Track spend by route before comparing costs

These illustrative rates are deliberately invented; they are not current provider prices or receipts from this Mac. They show how to retain tokens, rates and task costs in a document you can check.

| Task | Input tokens | Output tokens | Input $/M | Output $/M | Cost, USD |
| --- | ---: | ---: | ---: | ---: | ---: |
| Research | 200000 | 20000 | 2.00 | 8.00 | 0.560 |
| Draft | 100000 | 15000 | 1.00 | 4.00 | 0.160 |
| Check | 80000 | 10000 | 1.00 | 4.00 | 0.120 |
| Revise | 50000 | 8000 | 1.00 | 4.00 | 0.082 |
| **Total** | **430000** | **53000** | — | — | **0.922** |

Cost is input tokens / 1,000,000 × input rate, plus output tokens / 1,000,000 × output rate. Retried billable runs belong in the total. Local inference has no provider token bill, but still uses hardware, electricity and your time.

```chart
chartType: Waterfall Chart
title: Research accounts for most of this sample bill
subtitle: Invented rates and runs · USD · total $0.922
source: Fictional bundled example; replace with your own records
data:
  - task: Research
    cost: 0.56
  - task: Draft
    cost: 0.16
  - task: Check
    cost: 0.12
  - task: Revise
    cost: 0.082
semantic_types:
  task: Category
  cost: Amount
encodings:
  x:
    field: task
  y:
    field: cost
```

For actual work, read the route and cost Flow reports for the run. [[Model Arena]] presents published performance snapshots; this example bill must never be used as measured model evidence.
