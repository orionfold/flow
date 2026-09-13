---
title: Business Review Refresh
tags: ["business-review", "example"]
sources:
  records: Quarterly Close.md#table:Quarters
derive:
  typedRecords:
    from: records
    steps:
      - calculate: coalesce(revenue_m, 'missing') * 1
        as: revenue_m
      - calculate: coalesce(gross_margin_pct, 'missing') * 1
        as: gross_margin_pct
      - calculate: coalesce(customers, 'missing') * 1
        as: customers
      - calculate: coalesce(operating_income_m, 'missing') * 1
        as: operating_income_m
  gross:
    from: typedRecords
    steps:
      - calculate: revenue_m * gross_margin_pct / 100
        as: gross_profit
let:
  revenue:
    sum: revenue_m
    of: typedRecords
  profit:
    sum: operating_income_m
    of: typedRecords
  grossProfit:
    sum: gross_profit
    of: gross
emit:
  quarters:
    from: typedRecords
    steps:
      - sort: quarter
  summary:
    - metric: Revenue, $M
      value: '{round(revenue, 2)}'
    - metric: Operating income, $M
      value: '{round(profit, 2)}'
    - metric: Gross margin, %
      value: '{round(grossProfit / revenue * 100, 1)}'
---
# Business Review Refresh

This saved definition reads the records inside this folder and writes a dated summary. With this definition open, choose **File ▸ Edit Definition…** to inspect the sources, steps and results. It uses no model or web service.

| Part | Purpose |
| --- | --- |
| Source | Quarterly Close — authored records |
| Result | data/review-*.json — regenerated summary |
| Next change | Change one source record, run Gather, then inspect the bound view. |
