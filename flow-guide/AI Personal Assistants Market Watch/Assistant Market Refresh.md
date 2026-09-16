---
title: Assistant Market Refresh
sources:
  findings: Assistant Market Inputs.md#table:Evidence
  plans: Assistant Market Inputs.md#table:Plans
  signals: Assistant Market Inputs.md#table:Signals
let:
  findingCount: {count: finding_id, of: findings}
  captureCount: {distinct: capture_path, of: findings}
  productCount: {distinct: product, of: findings}
  reviewedCount: {count: finding_id, of: findings, where: "human_review == 'reviewed'"}
  exercisedCount: {count: finding_id, of: findings, where: "execution == 'exercised'"}
emit:
  summary:
    - {metric: Finding records, value: "{findingCount}"}
    - {metric: Retained source cards represented, value: "{captureCount}"}
    - {metric: Products represented, value: "{productCount}"}
    - {metric: Human-reviewed findings, value: "{reviewedCount}"}
    - {metric: Exercised findings, value: "{exercisedCount}"}
  coverage:
    from: findings
    steps:
      - {aggregate: product, count: finding_id, as: findings}
      - {sort: product}
  themes:
    from: findings
    steps:
      - {aggregate: theme, count: finding_id, as: findings}
      - {sort: theme}
  comparableCosts:
    from: plans
    steps:
      - {filter: "comparison_ready == 'yes' && currency == 'USD' && price_basis == 'individual-month'"}
      - {calculate: "monthly_usd * minimum_seats", as: minimum_monthly_usd}
      - {calculate: "round(minimum_monthly_usd * 12, 2)", as: twelve_month_scenario_usd}
      - {sort: minimum_monthly_usd}
      - {columns: [product, plan, minimum_monthly_usd, twelve_month_scenario_usd, credits, checked_at, source_url]}
  evidence:
    from: findings
    steps:
      - {sort: product}
  signals:
    from: signals
    steps:
      - {sort: event_at}
---
# Assistant Market Refresh

This definition reads the saved Evidence, Plans and Signals tables in [Assistant Market Inputs](Assistant%20Market%20Inputs.md). It produces deterministic JSON for the owner's bound tables and charts. It does not discover websites, judge claims or change human-review fields.

## Produced views

| Output | Meaning |
| --- | --- |
| summary | Finding, represented-card, product and explicitly reviewed/exercised counts. |
| coverage | Finding counts by product in this selected research set. |
| themes | Finding counts by research theme. |
| comparableCosts | Compatible monthly subscription costs and twelve-payment scenarios. |
| evidence | Every saved finding, ordered by product. |
| signals | Saved seed events, ordered by event date; no inferred semantic changes. |

## First run and future runs

The bundled JSON is an authored preview of twenty findings, not a recorded run. The saved inputs contain twenty-two. The first successful Gather uses all saved rows; later runs include whatever you deliberately save in the input tables. Counts measure retained evidence, not product quality or market share.

Opening this file in the definition editor lets you inspect the method behind the views. Editing a definition changes a draft until you save it; saving does not run it.
