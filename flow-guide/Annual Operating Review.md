---
title: Annual Operating Review
tags: [review, operating, annual]
---

# Annual Operating Review

**Owner:** operations · **Period:** FY2026 · **Status:** final

## Executive summary

The operating year closed with revenue up, churn down, and a working rhythm the team can sustain. This review walks through what shipped, what it cost, what broke, and what we learned — with the same candor we ask of our own documents.

![The operating year in summary](assets/growth-chart.jpeg)

*The operating year, quarter by quarter.*

| | Q1 | Q2 | Q3 | Q4 | Year |
| --- | ---: | ---: | ---: | ---: | ---: |
| Revenue | $3.9M | $4.4M | $5.2M | $5.7M | **$19.2M** |
| Gross margin | 79% | 80% | 82% | 83% | **81%** |
| Net revenue retention | 106% | 110% | 114% | 118% | **118%** |
| Customers at quarter end | 404 | 419 | 433 | 447 | **447** |
| Support median first response | 3.8h | 3.5h | 3.1h | 2.9h | **3.3h** |
| Headcount | 16 | 17 | 18 | 19 | **19** |

Revenue finished 34% ahead of plan, with the second half contributing nearly two-thirds of the total. Gross margin held above 80% all year, and the cost of serving each account fell steadily as routine work moved onto our own machines.

Churn told the quieter story. Logo retention improved every quarter, and the accounts that stayed grew: net revenue retention ended the year at 118%, up from 104%, driven almost entirely by teams expanding seats after their first full quarter.

```chart
chartType: Line Chart
title: The second half carried the year
subtitle: Revenue by quarter, FY2026, in millions
source: Finance close, audited
data:
  - {quarter: Q1, value: 3.9}
  - {quarter: Q2, value: 4.4}
  - {quarter: Q3, value: 5.2}
  - {quarter: Q4, value: 5.7}
semantic_types: {quarter: Category, value: Quantity}
encodings:
  x: {field: quarter}
  y: {field: value}
```

The operating rhythm matured alongside the numbers. Quarterly reviews ran on schedule, every initiative carried an owner and a measurable outcome, and misses were written up with the same care as wins — next year's plan stands on that record.

The pages that follow walk through each function in turn — product, growth, revenue, reliability, research, platform, and team — and close with the misses and the outlook.

## The product year

Four major releases shipped on the published cadence. Each one moved through the same discipline: a written specification, a measurable acceptance bar, and a retrospective filed beside the plan rather than in someone's notes.

| Release | Shipped | Headline capability | Cycle time |
| --- | --- | --- | ---: |
| 26.1 | March | Approval gate on every agency run | 11 weeks |
| 26.2 | June | Evidence records bound to exact bytes | 12 weeks |
| 26.3 | September | Local model runtime, zero install | 13 weeks |
| 26.4 | December | Receipts companion and history | 11 weeks |

```chart
chartType: Grouped Bar Chart
title: Cadence held while scope per release grew
subtitle: Weeks per release cycle, FY2026
data:
  - {release: 26.1, measure: Specification, value: 3}
  - {release: 26.1, measure: Build, value: 6}
  - {release: 26.1, measure: Review, value: 2}
  - {release: 26.2, measure: Specification, value: 3}
  - {release: 26.2, measure: Build, value: 7}
  - {release: 26.2, measure: Review, value: 2}
  - {release: 26.3, measure: Specification, value: 4}
  - {release: 26.3, measure: Build, value: 7}
  - {release: 26.3, measure: Review, value: 2}
  - {release: 26.4, measure: Specification, value: 3}
  - {release: 26.4, measure: Build, value: 6}
  - {release: 26.4, measure: Review, value: 2}
semantic_types: {release: Category, value: Quantity, measure: Category}
encodings:
  x: {field: release}
  y: {field: value}
  color: {field: measure}
```

The roadmap stayed honest about maturity: shipped, specified, and planned were never blurred into a single reassuring list. Every experiment ended with a written verdict, even the ones that ended quietly, because an unrecorded negative result gets rediscovered at full cost.

## Customer growth

Self-serve signups doubled in the second half of the year. The partner channel, opened in March, contributed its first six-figure quarter by December — later than planned and larger than modelled.

| Channel | New customers | Revenue | % of new revenue | CAC payback |
| --- | ---: | ---: | ---: | ---: |
| Direct sales | 34 | $2.9M | 58% | 14 months |
| Partner | 27 | $1.3M | 26% | 9 months |
| Self-serve | 58 | $0.8M | 16% | 4 months |
| **Total** | **119** | **$5.0M** | **100%** | **11 months** |

```chart
chartType: Donut Chart
title: Partner revenue arrived late and landed hard
subtitle: Share of new revenue by channel, FY2026
data:
  - {channel: Direct sales, value: 58}
  - {channel: Partner, value: 26}
  - {channel: Self-serve, value: 16}
semantic_types: {channel: Category, value: Quantity}
encodings:
  theta: {field: value}
  color: {field: channel}
```

Partners received the same enablement materials the internal team uses, which kept the story consistent at every remove and cut partner onboarding from six weeks to three.

## Revenue and margin

Subscription revenue grew steadily every quarter, and expansion revenue outpaced new business in the second half — the first year that has been true.

| | FY2025 | FY2026 | Change |
| --- | ---: | ---: | ---: |
| New business | $4.4M | $5.0M | +14% |
| Expansion | $2.6M | $5.3M | **+104%** |
| Renewal | $7.3M | $8.9M | +22% |
| **Total** | **$14.3M** | **$19.2M** | **+34%** |
| Cost of revenue | $3.1M | $3.6M | +16% |
| **Gross profit** | **$11.2M** | **$15.6M** | **+39%** |

**Expansion doubling is the number that matters here.** It means the product earned more room inside accounts that already had it — a cheaper and more durable kind of growth than new logos, and the reason net revenue retention reached 118%.

```chart
chartType: Area Chart
title: Expansion overtook new business in the second half
subtitle: Revenue by type, quarterly, in millions
data:
  - {quarter: Q1, measure: New business, value: 1.4}
  - {quarter: Q2, measure: New business, value: 1.3}
  - {quarter: Q3, measure: New business, value: 1.2}
  - {quarter: Q4, measure: New business, value: 1.1}
  - {quarter: Q1, measure: Expansion, value: 0.9}
  - {quarter: Q2, measure: Expansion, value: 1.2}
  - {quarter: Q3, measure: Expansion, value: 1.5}
  - {quarter: Q4, measure: Expansion, value: 1.7}
semantic_types: {quarter: Category, value: Quantity, measure: Category}
encodings:
  x: {field: quarter}
  y: {field: value}
  color: {field: measure}
```

Costs were reviewed monthly with the same discipline as revenue, and every anomaly received a written explanation with a named owner. Nothing in the ledger is estimated after the fact; the figure recorded is the figure observed.

## Reliability and support

Median first response stayed under four hours all year while the customer base grew by a third. Two incidents crossed the severity-one line, both resolved inside the published window, both written up in public.

| | Target | FY2026 actual |
| --- | ---: | ---: |
| Uptime | 99.9% | **99.94%** |
| Median first response | < 4h | **3.3h** |
| Median resolution | < 2 days | **1.4 days** |
| Severity-one incidents | — | **2** |
| Incidents with public write-up | 100% | **100%** |
| Tickets per customer per month | < 0.8 | **0.6** |

```chart
chartType: Line Chart
title: Response time fell while the customer base grew
subtitle: Median first response in hours, against customers
data:
  - {quarter: Q1, measure: First response (hours), value: 3.8}
  - {quarter: Q2, measure: First response (hours), value: 3.5}
  - {quarter: Q3, measure: First response (hours), value: 3.1}
  - {quarter: Q4, measure: First response (hours), value: 2.9}
semantic_types: {quarter: Category, value: Quantity, measure: Category}
encodings:
  x: {field: quarter}
  y: {field: value}
  color: {field: measure}
```

The two severity-one incidents shared a cause: a dependency upgrade applied without a staged rollout. The rollout policy changed in September and neither pattern has recurred.

## What the research said

Interview after interview repeated one theme: people do not distrust automation, they distrust automation they cannot inspect. The approval step is not friction to these teams — it is the reason the feature is usable at all.

![Research notes from the customer study](assets/research-desk.jpeg)

*Forty-one interviews across three segments, coded twice.*

| Theme | Mentions | Segments | Shipped response |
| --- | ---: | --- | --- |
| Wants to see the change before it lands | 38 | All | Approval gate (26.1) |
| Needs a record of what ran and why | 31 | Enterprise, mid-market | Evidence records (26.2) |
| Will not send documents off the machine | 24 | Enterprise | Local runtime (26.3) |
| Wants the record to travel with the file | 19 | All | Receipts companion (26.4) |
| Asked for fully autonomous editing | 3 | Self-serve | Not planned |

**Three requests for autonomy against thirty-eight for inspection.** That ratio decided the roadmap more than any competitive pressure did, and it is worth restating whenever the autonomous framing resurfaces.

## Platform investments

The document engine, search, and the review surface all received sustained investment. Search and the engine were rebuilt rather than patched, which cost a quarter and bought back years.

| Area | Investment | Measured result |
| --- | ---: | --- |
| Document engine | 4.5 eng-quarters | Save latency 21s → 0.37s |
| Search | 3.0 eng-quarters | Vault walk 65s → async, no blocking |
| Review surface | 2.5 eng-quarters | Approval-to-save under 2s |
| Local runtime | 4.0 eng-quarters | Zero-install first run |

```chart
chartType: Bar Chart
title: Where engineering time went
subtitle: Engineer-quarters by area, FY2026
data:
  - {area: Document engine, value: 4.5}
  - {area: Local runtime, value: 4.0}
  - {area: Search, value: 3.0}
  - {area: Review surface, value: 2.5}
semantic_types: {area: Category, value: Quantity}
encodings:
  x: {field: value}
  y: {field: area}
```

We measured before we optimized, and twice the measurement contradicted the intuition — which is exactly why we measure. Both times the slow path was not the one the team would have chosen to fix.

## Team and operating rhythm

The company stayed deliberately small. Writing culture carried the weight that meetings otherwise would: the plan, the evidence, and the decision live in the same file and travel together.

![How the work moves through the company](assets/layered-flows.jpeg)

*Plan, evidence, decision — one file, one thread.*

| | FY2025 | FY2026 |
| --- | ---: | ---: |
| Employees at year end | 15 | **19** |
| Revenue per employee | $953k | **$1.01M** |
| Voluntary attrition | 1 | **0** |
| Median tenure | 1.8 years | **2.4 years** |
| Recurring meetings per week | 6 | **4** |

Hiring stayed deliberately slow. Every role had to be justified by work already overflowing its owner, and the team ended the year at nineteen people — four more than January, each addition preceded by a written case.

The quarterly review held its shape: every initiative carried an owner, a measurable outcome, and a written retrospective filed beside the plan. The weekly review reads the record rather than reconstructing it.

## Honest misses

The partner enablement program slipped a quarter and cost us two warm design partners. Two onboarding cohorts ran without a written retrospective, which is exactly the discipline this document claims to hold.

| Miss | Cost | Root cause | Status |
| --- | --- | --- | --- |
| Partner enablement slipped a quarter | 2 design partners | No owner until March | Owned since Q2 |
| Two cohorts without retrospectives | Unmeasured | Process not enforced | Enforced since Q3 |
| Self-serve revenue fell 35% | $0.8M | Deliberate de-prioritisation | Accepted |
| Severity-one incidents ×2 | 4.1 hours downtime | Unstaged dependency upgrade | Policy changed |

**The self-serve decline was a choice, not a failure — but it is recorded here rather than in the wins.** We moved the team to enterprise onboarding mid-year and self-serve received no attention for two quarters. If it declines again next year without a decision behind it, that is a miss.

## Outlook

Next year is about compounding: reusable briefs that carry context forward, richer records of what ran and why, and a first-run experience that needs no setup at all — open a folder and the work simply starts.

| Priority | Measure of success | Owner |
| --- | --- | --- |
| Reusable briefs | Context carried across runs without re-entry | Product |
| Richer run records | Every run inspectable a year later | Platform |
| Zero-setup first run | Useful work inside five minutes of install | Product |
| Partner channel at scale | Partner revenue > 35% of new | Growth |

The roadmap stays honest about maturity: shipped, specified, and planned are never blurred into a single reassuring list. Next year's review will read this one and say plainly which of these four happened.
