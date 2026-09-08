---
title: Annual Report — Shareholder Letter
tags: [annual-report, shareholders, founder, finance]
---

# To our shareholders

**Fiscal year 2026 · Meridian Software · Filed 14 November 2026**

We finished the year at $19.2M in revenue, up 34%, profitable for the second half, and with more customers renewing than in any prior year. This letter is about what produced that, and about the two things we got wrong.

![The boardroom after the November meeting](assets/boardroom-annual.jpeg)

*The room where this year's figures were signed off.*

## Five-year summary

| | FY2022 | FY2023 | FY2024 | FY2025 | FY2026 |
| --- | ---: | ---: | ---: | ---: | ---: |
| Revenue | $2.1M | $4.8M | $8.9M | $14.3M | **$19.2M** |
| Growth | — | 129% | 85% | 61% | **34%** |
| Gross profit | $1.4M | $3.4M | $6.6M | $11.2M | **$15.6M** |
| Gross margin | 67% | 71% | 74% | 78% | **81%** |
| Operating expenses | $3.0M | $5.1M | $9.7M | $12.4M | **$15.2M** |
| Operating income | −$1.6M | −$1.7M | −$3.1M | −$1.2M | **$0.4M** |
| Free cash flow | −$1.9M | −$2.0M | −$3.1M | −$1.2M | **$0.4M** |
| Cash at year end | $6.2M | $9.4M | $6.3M | $5.1M | **$5.5M** |
| Employees | 6 | 9 | 11 | 15 | **19** |
| Revenue per employee | $350k | $533k | $809k | $953k | **$1.01M** |

```chart
chartType: Line Chart
title: Margin improved every year while growth normalised
subtitle: Percent, FY2022–FY2026
source: Audited statements
data:
  - {year: FY2022, measure: Gross margin, value: 67}
  - {year: FY2023, measure: Gross margin, value: 71}
  - {year: FY2024, measure: Gross margin, value: 74}
  - {year: FY2025, measure: Gross margin, value: 78}
  - {year: FY2026, measure: Gross margin, value: 81}
  - {year: FY2023, measure: Revenue growth, value: 129}
  - {year: FY2024, measure: Revenue growth, value: 85}
  - {year: FY2025, measure: Revenue growth, value: 61}
  - {year: FY2026, measure: Revenue growth, value: 34}
semantic_types: {year: Category, value: Quantity, measure: Category}
encodings:
  x: {field: year}
  y: {field: value}
  color: {field: measure}
```

## Revenue by segment

| Segment | FY2025 | FY2026 | Change | % of total |
| --- | ---: | ---: | ---: | ---: |
| Enterprise | $7.9M | $12.4M | +57% | 65% |
| Mid-market | $4.1M | $5.3M | +29% | 28% |
| Self-serve | $2.3M | $1.5M | **−35%** | 8% |
| **Total** | **$14.3M** | **$19.2M** | **+34%** | **100%** |

```chart
chartType: Stacked Bar Chart
title: Enterprise absorbed the self-serve decline
subtitle: Revenue by segment and fiscal year, $M
source: Audited statements, FY2026
data:
  - {year: FY2024, segment: Enterprise, revenue: 4.2}
  - {year: FY2024, segment: Mid-market, revenue: 2.6}
  - {year: FY2024, segment: Self-serve, revenue: 2.1}
  - {year: FY2025, segment: Enterprise, revenue: 7.9}
  - {year: FY2025, segment: Mid-market, revenue: 4.1}
  - {year: FY2025, segment: Self-serve, revenue: 2.3}
  - {year: FY2026, segment: Enterprise, revenue: 12.4}
  - {year: FY2026, segment: Mid-market, revenue: 5.3}
  - {year: FY2026, segment: Self-serve, revenue: 1.5}
semantic_types: {year: Category, revenue: Quantity, segment: Category}
encodings:
  x: {field: year}
  y: {field: revenue}
  color: {field: segment}
```

```chart
chartType: Waterfall Chart
title: How $14.3M became $19.2M
subtitle: ARR bridge, FY2025 to FY2026, $M
source: Audited statements
data:
  - {step: FY2025 ARR, amount: 14.3}
  - {step: New customers, amount: 3.1}
  - {step: Expansion, amount: 4.4}
  - {step: Contraction, amount: -1.2}
  - {step: Churn, amount: -1.4}
semantic_types: {step: Category, amount: Quantity}
encodings:
  x: {field: step}
  y: {field: amount}
```

Expansion contributed more than new business — $4.4M against $3.1M. That is the 118% retention figure expressed in dollars.

## Revenue by geography

| Region | FY2025 | FY2026 | Change | % of total |
| --- | ---: | ---: | ---: | ---: |
| North America | $9.6M | $12.1M | +26% | 63% |
| Europe | $3.4M | $5.4M | +59% | 28% |
| Asia-Pacific | $1.0M | $1.4M | +40% | 7% |
| Rest of world | $0.3M | $0.3M | — | 2% |
| **Total** | **$14.3M** | **$19.2M** | **+34%** | **100%** |

```chart
chartType: Bar Chart
title: Europe grew fastest, without a local sales team
subtitle: Revenue growth by region, FY2026
highlight: Europe
data:
  - {region: North America, growth: 26}
  - {region: Europe, growth: 59}
  - {region: Asia-Pacific, growth: 40}
  - {region: Rest of world, growth: 0}
semantic_types: {region: Category, growth: Quantity}
encodings:
  x: {field: region}
  y: {field: growth}
```

Europe grew fastest off a smaller base, entirely through referral and partner motion rather than a local sales team.

## Customers and retention

| | FY2024 | FY2025 | FY2026 |
| --- | ---: | ---: | ---: |
| Customers at year end | 284 | 391 | **447** |
| New customers added | 118 | 152 | **119** |
| Customers lost | 41 | 45 | **63** |
| Logo retention | 86% | 88% | **86%** |
| Net revenue retention | 98% | 104% | **118%** |
| Average contract value | $31k | $37k | **$43k** |
| Customers over $100k | 9 | 17 | **31** |

**Net revenue retention of 118% carried the year.** Note the tension in this table: logo retention *fell* while revenue retention rose sharply. We lost more customers than ever, and they were small ones; the accounts that stayed expanded. That is a good outcome this year and a fragile one to depend on.

```chart
chartType: Line Chart
title: Revenue retention rose while logo retention did not
subtitle: Percent, by fiscal year
data:
  - {year: FY2024, measure: Net revenue retention, value: 98}
  - {year: FY2025, measure: Net revenue retention, value: 104}
  - {year: FY2026, measure: Net revenue retention, value: 118}
  - {year: FY2024, measure: Logo retention, value: 86}
  - {year: FY2025, measure: Logo retention, value: 88}
  - {year: FY2026, measure: Logo retention, value: 86}
semantic_types: {year: Category, value: Quantity, measure: Category}
encodings:
  x: {field: year}
  y: {field: value}
  color: {field: measure}
```

## Operating expenses

| | FY2025 | % of revenue | FY2026 | % of revenue |
| --- | ---: | ---: | ---: | ---: |
| Research and development | $5.4M | 38% | $6.6M | **34%** |
| Sales and marketing | $4.6M | 32% | $5.2M | **27%** |
| General and administrative | $2.4M | 17% | $3.4M | **18%** |
| **Total operating expenses** | **$12.4M** | **87%** | **$15.2M** | **79%** |

```chart
chartType: Grouped Bar Chart
title: Every function fell as a share of revenue except G&A
subtitle: Operating expense as percent of revenue
data:
  - {function: R&D, year: FY2025, pct: 38}
  - {function: R&D, year: FY2026, pct: 34}
  - {function: S&M, year: FY2025, pct: 32}
  - {function: S&M, year: FY2026, pct: 27}
  - {function: G&A, year: FY2025, pct: 17}
  - {function: G&A, year: FY2026, pct: 18}
semantic_types: {function: Category, pct: Quantity, year: Category}
encodings:
  x: {field: function}
  y: {field: pct}
  group: {field: year}
```

Every line grew in absolute terms and fell as a share of revenue except G&A, which rose on audit, insurance and the first full year of a finance function.

## Headcount

| Function | FY2025 | FY2026 | Change |
| --- | ---: | ---: | ---: |
| Engineering | 7 | 9 | +2 |
| Product and design | 3 | 4 | +1 |
| Sales | 2 | 3 | +1 |
| Marketing | 1 | 1 | — |
| Support | 1 | 1 | — |
| Finance and operations | 1 | 1 | — |
| **Total** | **15** | **19** | **+4** |

```chart
chartType: Pie Chart
title: Two-thirds of the company builds the product
subtitle: Headcount by function, FY2026
data:
  - {function: Engineering, people: 9}
  - {function: Product and design, people: 4}
  - {function: Sales, people: 3}
  - {function: Marketing, people: 1}
  - {function: Support, people: 1}
  - {function: Finance and operations, people: 1}
semantic_types: {function: Category, people: Quantity}
encodings:
  size: {field: people}
  color: {field: function}
```

Four hires against a plan of nine. Each addition was preceded by a written case that work was already overflowing its owner.

## Quarterly detail

| | Q1 | Q2 | Q3 | Q4 | FY2026 |
| --- | ---: | ---: | ---: | ---: | ---: |
| Revenue | $4.1M | $4.6M | $5.0M | $5.5M | $19.2M |
| Gross margin | 79% | 80% | 82% | 82% | 81% |
| Operating income | −$0.4M | −$0.2M | $0.3M | $0.7M | $0.4M |
| New customers | 34 | 31 | 28 | 26 | 119 |
| Net revenue retention | 108% | 112% | 115% | 118% | 118% |

```chart
chartType: Area Chart
title: The company crossed into profit in Q3
subtitle: Quarterly operating income, $M
data:
  - {quarter: Q1, income: -0.4}
  - {quarter: Q2, income: -0.2}
  - {quarter: Q3, income: 0.3}
  - {quarter: Q4, income: 0.7}
semantic_types: {quarter: Category, income: Quantity}
encodings:
  x: {field: quarter}
  y: {field: income}
```

New customer additions fell every quarter. Revenue rose anyway, because expansion more than covered it — the same tension as the retention table, and the single most important thing in this document.

## What worked

**Existing customers expanded on their own.** When we asked why, in [[Customer Interviews]], nobody mentioned a salesperson. Expansion came from teams adding seats after their first full quarter.

**We stopped shipping features nobody asked for.** The roadmap moved to outcomes in January. Cycle time fell from eleven weeks to four, and the share of shipped work customers used within a month went from 40% to 71%.

**Costs behaved.** Gross margin improved three points while headcount grew, as routine work moved onto our own hardware. The detail is in [[Cost of This Quarter]].

## What did not

**Self-serve fell 35% and we were slow to see it.** Two competitors cut entry pricing in June; conversion fell through July and August before it was raised as a problem. The number was visible the whole time — a monitoring failure more than a pricing one. The competitive detail is in [[Market Landscape]].

**We under-invested in what was working.** Referrals produced 43% of bookings with no owner and no budget, as [[Sales Report — Q3]] sets out. [[How We Decided]] records the decision to fund it, which should have been made a year earlier.

**New customer count declined every quarter.** Masked by expansion this year. It will not be maskable in FY2027.

## FY2027 commitments

| # | Commitment | Measure | Owner |
| --- | --- | --- | --- |
| 1 | Fund the referral motion | Referral bookings ≥ $2.4M | Sales |
| 2 | Resolve self-serve | Attribution study by 31 Jan, then decide | Marketing |
| 3 | Reverse the new-logo decline | ≥ 150 new customers | Sales |
| 4 | Hold profitability | Operating income ≥ $1.0M | Finance |
| 5 | Keep hiring disciplined | ≤ 6 hires, each with a written case | CEO |

## A closing note

We publish our misses in the same document as our wins, at the same level of detail. It is not modesty; a board that only hears about wins cannot help with anything else.

Thank you for the year.

**Priya Raman**, Chief Executive

---

*Figures are audited except where noted. Segment and geography splits are management estimates using the same allocation basis as prior years.*
