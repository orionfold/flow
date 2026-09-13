---
title: Charts — Composition
tags: [charts-gallery, reference, fictional-example]
---
# Charts — Composition

[[Charts Gallery]] · Previous: [[Charts — Time Series]] · Next: [[Charts — Distributions]]

**Show a whole, its parts or the changes that reconcile it.**

> Every exhibit on this page uses fictional teaching data or an authored scenario. Source labels describe the example; they are not reports, measured Flow benchmarks or product guarantees.

| Form | Use it for |
| --- | --- |
| Stacked bar chart | Compare totals and their components together |
| Waterfall chart | Reconcile an opening amount through signed movements to a closing amount |
| Pie chart | Show a few nonnegative parts of a single meaningful whole |
| Donut chart | Use a compact part-to-whole view with a clear total nearby |
| Streamgraph | Explore how several parts change over time |
| Rose chart | Explore ordered cyclical categories such as weekdays |

First define what adds to the whole. A spend bridge, a share of revenue and a changing traffic mix are different questions.

## The exhibits

### Stacked bar chart

Compare totals and their components together. Only the first component has a common baseline, so use grouped bars when precise middle-component comparisons matter.

Source: a table with a category column, a part column and a value column, where the parts of each category add up to a meaningful whole: cost by team and category, headcount by office and function.

```chart
chartType: Stacked Bar Chart
title: Cloud is the largest spend category for every team
subtitle: Monthly run-rate by team and cost category, $k
source: Fictional teaching sample — FinOps, July 2026
data:
  - {team: Platform, category: Cloud, cost: 142}
  - {team: Platform, category: Tooling, cost: 38}
  - {team: Platform, category: Vendors, cost: 21}
  - {team: Data, category: Cloud, cost: 118}
  - {team: Data, category: Tooling, cost: 27}
  - {team: Data, category: Vendors, cost: 44}
  - {team: Product, category: Cloud, cost: 36}
  - {team: Product, category: Tooling, cost: 31}
  - {team: Product, category: Vendors, cost: 19}
  - {team: Research, category: Cloud, cost: 97}
  - {team: Research, category: Tooling, cost: 12}
  - {team: Research, category: Vendors, cost: 8}
semantic_types: {team: Category, category: Category, cost: Amount}
encodings:
  x: {field: team}
  y: {field: cost}
  color: {field: category}
```

[[Charts Gallery]]

### Waterfall chart

Reconcile an opening amount through signed movements to a closing amount. Check the arithmetic and distinguish totals from changes; a missing movement cannot be repaired by the chart.

Source: a table of named steps and signed amounts, from an opening figure through additions and subtractions to a closing one: a revenue bridge, a headcount reconciliation.

```chart
chartType: Waterfall Chart
title: Expansion carried ARR past churn and contraction
subtitle: ARR bridge, Q2 → Q3 FY26, $k
source: Fictional teaching sample — Finance close
data:
  - {step: Opening ARR, change: 4820}
  - {step: New logos, change: 412}
  - {step: Expansion, change: 275}
  - {step: Contraction, change: -96}
  - {step: Churn, change: -148}
  - {step: Closing ARR, change: 5263}
semantic_types: {step: Category, change: Amount}
encodings:
  x: {field: step}
  y: {field: change}
```

[[Charts Gallery]]

### Pie chart

Show a few nonnegative parts of a single meaningful whole. State the denominator; use bars for close values, many categories or overlapping groups.

Source: a short table of parts and their share: five or fewer slices that add to a whole, such as revenue by segment or time by activity.

```chart
chartType: Pie Chart
title: Teams account for over half of revenue
subtitle: ARR by plan, share of total
source: Fictional teaching sample — Finance, July 2026
highlight: Team
data:
  - {plan: Team, share: 54}
  - {plan: Pro, share: 31}
  - {plan: Enterprise, share: 11}
  - {plan: Education, share: 4}
semantic_types: {plan: Category, share: Percentage}
encodings:
  size: {field: share}
  color: {field: plan}
```

[[Charts Gallery]]

### Donut chart

Use a compact part-to-whole view with a clear total nearby. Angles are harder to compare than lengths; keep exact amounts available in a table or paired bar chart.

Source: the same parts-and-share table as a pie, when a headline number belongs in the centre or the chart sits inline beside text.

```chart
chartType: Donut Chart
title: Most Agency runs stay on the Mac
subtitle: Runs by provider, last 30 days
source: Fictional teaching sample — Fictional receipt-shaped sample
highlight: Flow Runtime (local)
data:
  - {provider: Flow Runtime (local), runs: 1412}
  - {provider: Apple Intelligence, runs: 388}
  - {provider: Hosted API, runs: 206}
semantic_types: {provider: Category, runs: Count}
encodings:
  size: {field: runs}
  color: {field: provider}
```

[[Charts Gallery]]

### Streamgraph

Explore how several parts change over time. The moving baseline helps show the mix but makes exact cross-period values harder to compare; use lines when precision is the priority.

Source: a long table of date, category and value with several categories per date, such as share of attention, traffic by channel or tickets by product, when the story is how the mix shifts.

```chart
chartType: Streamgraph
title: Organic search overtook paid by spring
subtitle: Monthly site visits by channel, thousands
source: Fictional teaching sample — Web analytics
data:
  - {month: 2026-01, channel: Paid, visits: 62}
  - {month: 2026-01, channel: Organic, visits: 41}
  - {month: 2026-01, channel: Referral, visits: 18}
  - {month: 2026-01, channel: Direct, visits: 24}
  - {month: 2026-02, channel: Paid, visits: 58}
  - {month: 2026-02, channel: Organic, visits: 47}
  - {month: 2026-02, channel: Referral, visits: 21}
  - {month: 2026-02, channel: Direct, visits: 26}
  - {month: 2026-03, channel: Paid, visits: 51}
  - {month: 2026-03, channel: Organic, visits: 56}
  - {month: 2026-03, channel: Referral, visits: 25}
  - {month: 2026-03, channel: Direct, visits: 29}
  - {month: 2026-04, channel: Paid, visits: 44}
  - {month: 2026-04, channel: Organic, visits: 68}
  - {month: 2026-04, channel: Referral, visits: 31}
  - {month: 2026-04, channel: Direct, visits: 33}
  - {month: 2026-05, channel: Paid, visits: 40}
  - {month: 2026-05, channel: Organic, visits: 79}
  - {month: 2026-05, channel: Referral, visits: 36}
  - {month: 2026-05, channel: Direct, visits: 35}
  - {month: 2026-06, channel: Paid, visits: 38}
  - {month: 2026-06, channel: Organic, visits: 88}
  - {month: 2026-06, channel: Referral, visits: 39}
  - {month: 2026-06, channel: Direct, visits: 38}
semantic_types: {month: YearMonth, channel: Category, visits: Count}
encodings:
  x: {field: month}
  y: {field: visits}
  color: {field: channel}
```

[[Charts Gallery]]

### Rose chart

Explore ordered cyclical categories such as weekdays. Explain the period and magnitude; radius and area can give different visual impressions, so keep the underlying values available.

Source: a table of cyclical categories and a magnitude, such as hours of the day, months or compass directions, where a polar layout shows the cycle.

```chart
chartType: Rose Chart
title: Wednesday has the highest sample ticket volume
subtitle: Tickets by weekday, average per day
source: Fictional teaching sample — Support desk
data:
  - {weekday: Mon, tickets: 84}
  - {weekday: Tue, tickets: 102}
  - {weekday: Wed, tickets: 118}
  - {weekday: Thu, tickets: 97}
  - {weekday: Fri, tickets: 71}
  - {weekday: Sat, tickets: 22}
  - {weekday: Sun, tickets: 15}
semantic_types: {weekday: Day, tickets: Count}
encodings:
  x: {field: weekday}
  y: {field: tickets}
```

[[Charts Gallery]]

## Use a form with your own records

Copy the whole **Charts Gallery** folder and add that copy to Flow first. Open [[Gallery Data]] to practise with a table you can edit. [[Charts — Living Example]] shows the refresh path. These reference exhibits keep their own embedded examples; they do not change when the practice table changes.

For a new exhibit, open a suitable example in the chart editor or select your own source rows and use Visualize. Keep the units and source explanation with the result. Visualize uses your configured Agency route; inspect its proposal before applying. Authored Mermaid diagrams need deliberate text edits; they are not automatically maintained from the table.

[[Charts Gallery]] · Previous: [[Charts — Time Series]] · Next: [[Charts — Distributions]]
