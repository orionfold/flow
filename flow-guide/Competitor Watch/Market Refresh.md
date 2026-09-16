---
title: Market Refresh
sources:
  findings: Market Inputs.md#table:Evidence
  plans: Market Inputs.md#table:Plans
let:
  findingCount: {count: source_id, of: findings}
  captureCount: {distinct: capture_path, of: findings}
  reviewedCount: {count: source_id, of: findings, where: "human_review == 'reviewed'"}
emit:
  summary:
    - {metric: Finding records, value: "{findingCount}"}
    - {metric: Distinct captures, value: "{captureCount}"}
    - {metric: Human-reviewed findings, value: "{reviewedCount}"}
  coverage:
    from: findings
    steps:
      - {aggregate: product, count: source_id, as: findings}
      - {sort: product}
  themes:
    from: findings
    steps:
      - {aggregate: theme, count: source_id, as: findings}
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
---
# Market Refresh

One definition reads the saved Evidence and Plans body tables. Counts are coverage of this chosen research set. Human review changes only when the founder edits that field. Missing offer units are excluded rather than turned into zero. No model, arbitrary HTML capture or date-arithmetic freshness claim is hidden here.

Run Jobs after saving the inputs. The dated capture supplies the summary, product coverage, theme and packaging views. Existing values are a September 14, 2026 starting snapshot.

## Produced views

| Output | Meaning |
| --- | --- |
| Summary | Finding records, distinct captures and explicitly reviewed findings. |
| Coverage | Finding count by product in this chosen set. |
| Themes | Finding count by research topic. |
| Comparable costs | Only offers with compatible billing units. |
| Evidence | All saved findings, ordered by product. |
