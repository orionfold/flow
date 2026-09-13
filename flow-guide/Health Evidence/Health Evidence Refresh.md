---
title: Health Evidence Refresh
tags: [health, definition, fictional-example]
sources:
  settings: Health Evidence Settings.md#table:Settings
  packet: inputs/health-operations-*.md#table:Review
  weeks: inputs/health-operations-*.md#table:Weeks
derive:
  checkedWeeks:
    from: weeks
    steps:
      - {calculate: "scheduled > 0 ? round(missed / scheduled * 100, 1) : 'No denominator'", as: missed_pct}
      - {calculate: "scheduled - completed - missed - cancelled", as: difference}
      - {calculate: "'Missed appointments'", as: series}
let:
  threshold: {max: value, of: settings, where: "key == 'review_threshold_pct'"}
  scheduledTotal: {sum: scheduled, of: checkedWeeks}
  missedTotal: {sum: missed, of: checkedWeeks}
  pooledRate: "scheduledTotal > 0 ? round(missedTotal / scheduledTotal * 100, 1) : 'No denominator'"
  aboveThreshold: {count: week, of: checkedWeeks, where: "scheduled > 0 && missed_pct > threshold"}
emit:
  review:
    from: packet
    steps:
      - {columns: [team, as_of, unit]}
  weekly:
    from: checkedWeeks
    steps:
      - {sort: week}
      - {columns: [week, scheduled, completed, missed, cancelled, missed_pct, series]}
  summary:
    - {metric: Scheduled appointments, value: "{scheduledTotal}"}
    - {metric: Missed appointments, value: "{missedTotal}"}
    - {metric: "Missed share of all scheduled appointments, %", value: "{pooledRate}"}
  reviewThreshold:
    - {metric: "Review threshold, %", value: "{threshold}"}
    - {metric: Weeks above the threshold, value: "{aboveThreshold}"}
  dataChecks:
    from: checkedWeeks
    steps:
      - {filter: "difference != 0 || scheduled <= 0 || completed < 0 || missed < 0 || cancelled < 0"}
      - {columns: [week, scheduled, completed, missed, cancelled, difference]}
---
# Health Evidence Refresh

This local definition calculates rates and displays count inconsistencies. It does not interpret symptoms, recommend treatment, read patient records, or discover a causal effect.

The pooled rate is the sum of missed appointments divided by the sum of scheduled appointments. The discussion threshold comes from [[Health Evidence Settings]]. `dataChecks` lists zero-denominator, negative-count, or unreconciled rows for human correction; it is not a full data-validation system and does not reject a capture automatically.

| Input | Result | Calculation boundary |
| --- | --- | --- |
| Weekly outcome counts | Weekly rates and pooled summary | Pooled rate uses total missed divided by total scheduled |
| Review threshold | Number of weeks above the threshold | Changes the review count, not observed rates |
| Outcome reconciliation | Data-check rows | Shows inconsistencies for correction; does not reject a capture |

The output is `data/health-evidence-<run-date>.json`. The source notes and interpretive text in [[Health Evidence]] remain authored. With this definition open, choose **File ▸ Edit Definition…** to inspect the calculations.
