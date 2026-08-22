---
title: Cost of This Quarter
tags: [cost, receipts, transparency]
---

# What this folder cost to produce

Every document in this folder was made with model assistance, and every run
was priced at the moment it happened. This page is the bill.

```chart
chartType: Waterfall Chart
title: Where the spend went
subtitle: US dollars, Q3 document work
data:
  - {step: Research, amount: 1.42}
  - {step: Drafting, amount: 0.96}
  - {step: Checking, amount: 0.71}
  - {step: Revisions, amount: 0.38}
semantic_types: {step: Category, amount: Quantity}
encodings:
  x: {field: step}
  y: {field: amount}
```

## The itemised total

| Document | Runs | Input tokens | Output tokens | Cost |
| --- | ---: | ---: | ---: | ---: |
| [[Quarterly Business Review]] | 7 | 184,200 | 21,400 | $1.04 |
| [[Revenue Dashboard]] | 4 | 96,800 | 12,100 | $0.58 |
| [[Market Landscape]] | 5 | 121,300 | 14,900 | $0.71 |
| [[Customer Interviews]] | 3 | 78,400 | 9,200 | $0.44 |
| [[How We Decided]] | 2 | 41,600 | 6,800 | $0.32 |
| **Total** | **21** | **522,300** | **64,400** | **$3.09** |

## Why the arithmetic is shown

A cost you cannot check is a number you have to take on faith, and the whole
point of a receipt is that you do not have to. The rates below are the ones
that were in force when these runs happened; multiply them out yourself.

| | Rate per million | Tokens | Line total |
| --- | ---: | ---: | ---: |
| Input | $0.97 | 522,300 | $0.507 |
| Output | $3.04 | 64,400 | $0.196 |
| | | **Sum** | **$0.703** |

The itemised table totals $3.09 rather than $0.70 because it includes eleven
research runs against a larger model at a higher rate, before the work moved
to the cheaper one. That difference is the kind of thing a summary number
hides and an itemised one cannot.

## What is not counted here

- **Your own time**, which is the expensive input and the one nothing meters.
- **Runs that failed** and were retried: three of the twenty-one produced
  nothing usable and are still billed above, because they were still spent.
- **Local models**, which cost nothing per run and are not in this table at
  all. If you route work to a model on your own machine, there is no line item
  to show you.

## Seeing this for your own work

Flow shows the meter for a run before you approve it, and records what it
actually cost after. Nothing in this folder ships with a stored receipt — the
numbers above are illustrative of a real quarter's shape, not a receipt Flow
issued on your machine. To see a real one, run an action yourself from
[[How We Decided]] and read the cost it reports.
