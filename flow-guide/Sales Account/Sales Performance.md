---
title: Sales Performance
tags: [sales, pipeline, report]
---

# Sales performance — Q3 2026

**Fictional team sales review.** Bookings are contracted value, not recognised revenue. The sample does not describe the Meridian opportunity.

Bookings finished at **$1.42M against a $1.30M quota**, 109% attainment, carried by two large deals that both closed in the final three weeks. The two late deals contributed $406k. Excluding them leaves $1.014M, or 78% of quota; Q4 needs its own forecast.

## Attainment

```chart
chartType: Bullet Chart
title: Attainment against quota by rep
subtitle: Q3 bookings, $k
data:
  - {rep: Alex, bookings: 512, quota: 400}
  - {rep: Jordan, bookings: 398, quota: 400}
  - {rep: Sam, bookings: 289, quota: 350}
  - {rep: Ravi, bookings: 221, quota: 150}
semantic_types: {rep: Category, bookings: Quantity, quota: Quantity}
encodings:
  y: {field: rep}
  x: {field: bookings}
  goal: {field: quota}
```

## The funnel

| Stage | Entered | Converted | Rate | Median days |
| --- | ---: | ---: | ---: | ---: |
| Qualified | 148 | 96 | 65% | 6 |
| Discovery | 96 | 61 | 64% | 11 |
| Proposal | 61 | 34 | 56% | 14 |
| Negotiation | 34 | 27 | 79% | 9 |
| **Closed won** | **27** | — | **18% of qualified** | — |

Proposal-to-negotiation is the leak: 56%, the worst stage, and it is where [[Meridian Proposal]] gets sent. Two reps rewrite that document from scratch each time; one uses a template and reports 71% in a small sample. Deal mix and sample counts are missing, so this is a hypothesis to test.

## Where the deals came from

```chart
chartType: Donut Chart
title: Bookings by source
subtitle: Q3, $k
data:
  - {source: Referral, amount: 604}
  - {source: Inbound, amount: 412}
  - {source: Outbound, amount: 288}
  - {source: Partner, amount: 116}
semantic_types: {source: Category, amount: Quantity}
encodings:
  size: {field: amount}
  color: {field: source}
```

Referral contributes 42.5% of sample bookings. Assign an owner to understand this channel before assuming it will repeat.

## Q4 pipeline

| | Count | Value | Weighted |
| --- | ---: | ---: | ---: |
| Commit | 9 | $410k | $369k |
| Best case | 14 | $680k | $340k |
| Pipeline | 31 | $1.9M | $285k |
| **Total** | **54** | **$2.99M** | **$994k** |

Against a $1.45M Q4 quota, weighted pipeline covers 69%. Historically we close about 1.4× weighted, which lands at roughly $1.39M — short, and the gap is real rather than a rounding problem.

## What we are doing

1. **Fix the proposal step.** One template, used by everyone, starting with the one that converts at 71%.
2. **Give referrals an owner.** Review acquisition cost and retention before choosing a budget.
3. **Stop counting the two whales as normal.** Q4 forecast assumes zero deals over $200k unless one is already in negotiation.

[[Account Brief]] shows how an individual opportunity keeps its own discovery evidence and open questions.
