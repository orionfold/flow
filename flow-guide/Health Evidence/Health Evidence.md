---
title: Health Evidence
category: business-teams
summary: "Aggregate service counts and an operational evidence review."
tags: [health, research, operations, living-workspace, fictional-example]
jobs:
  - kind: gather
    definition: Health Evidence Refresh.md
    into: data
    as: health-evidence
  - kind: keep-sources-fresh
    watch: [Health Evidence Settings.md, inputs, sources]
---
# Health Evidence

## Did the latest week change the question?

Maple Grove's fictional operations team wants to understand missed appointments. This brief keeps the counts, their denominators, and the limits of the evidence together. The sample shows a downward series; it does not establish that reminder wording caused it.

> **Teaching data only.** No patient information, diagnosis, treatment advice, or invented official studies. The work is organizing an operational review.

<!-- data: data/health-evidence-*.json#review -->
| Team | As of |
| --- | --- |
| Maple Grove clinic operations | 2026-09-12 |

## Read the rate alongside the count

Each point is missed appointments divided by all appointments scheduled for that week, including those later cancelled. A change in cancellation behavior can therefore change the rate.

```chart data: data/health-evidence-*.json#weekly
chartType: Line Chart
title: "Missed appointments as a share of the weekly schedule"
subtitle: "Percent · fictional weekly cohorts; points are observations, not an effect estimate"
source: "Local weekly snapshot; missed / scheduled × 100"
data:
  - {week: "2026-08-03", scheduled: 120, completed: 102, missed: 12, cancelled: 6, missed_pct: 10, series: "Missed appointments"}
  - {week: "2026-08-10", scheduled: 125, completed: 109, missed: 10, cancelled: 6, missed_pct: 8, series: "Missed appointments"}
  - {week: "2026-08-17", scheduled: 118, completed: 104, missed: 8, cancelled: 6, missed_pct: 6.8, series: "Missed appointments"}
  - {week: "2026-08-24", scheduled: 128, completed: 112, missed: 9, cancelled: 7, missed_pct: 7, series: "Missed appointments"}
  - {week: "2026-08-31", scheduled: 130, completed: 116, missed: 8, cancelled: 6, missed_pct: 6.2, series: "Missed appointments"}
  - {week: "2026-09-07", scheduled: 132, completed: 119, missed: 7, cancelled: 6, missed_pct: 5.3, series: "Missed appointments"}
semantic_types: {"week": "Date", "missed_pct": "Percentage", "series": "Category"}
encodings:
  x: {"field": "week"}
  y: {"field": "missed_pct"}
  color: {"field": "series", "scheme": "teals"}
```

<!-- data: data/health-evidence-*.json#weekly -->
| Week | Scheduled | Completed | Missed | Cancelled | Missed pct |
| --- | --- | --- | --- | --- | --- |
| 2026-08-03 | 120 | 102 | 12 | 6 | 10 |
| 2026-08-10 | 125 | 109 | 10 | 6 | 8 |
| 2026-08-17 | 118 | 104 | 8 | 6 | 6.8 |
| 2026-08-24 | 128 | 112 | 9 | 7 | 7 |
| 2026-08-31 | 130 | 116 | 8 | 6 | 6.2 |
| 2026-09-07 | 132 | 119 | 7 | 6 | 5.3 |

## Pool the underlying appointments, not the percentages

<!-- data: data/health-evidence-*.json#summary -->
| Metric | Value |
| --- | --- |
| Scheduled appointments | 753 |
| Missed appointments | 54 |
| Missed share of all scheduled appointments, % | 7.2 |

## What the evidence can carry

| Observation | Reasonable use | Question still open |
| --- | --- | --- |
| Every week has a visible denominator. | Check the size of the series and reproduce the rates. | Were the weekly cohorts comparable? |
| A later snapshot adds one completed week. | See whether the direction persists as data accumulates. | How much is ordinary variation? |
| Staff describe a reminder wording change. | Form a hypothesis for a future evaluation. | Did reminders cause any change? |

Read [[Health Evidence Sources]] before presenting an interpretation. The six-week sample supports a discussion, not a causal claim.

### A review threshold is a choice

This setting only helps the team select weeks to discuss. It does not classify care quality.

<!-- data: data/health-evidence-*.json#reviewThreshold -->
| Metric | Value |
| --- | --- |
| Review threshold, % | 6 |
| Weeks above the threshold | 5 |

### Check the counts before reading the trend

The table is empty in the supplied example because all outcome counts reconcile and every denominator is positive. If it gains a row, correct that input before using the summary; the refresh does not block an inconsistent packet automatically.

<!-- data: data/health-evidence-*.json#dataChecks -->
| Week | Scheduled | Completed | Missed | Cancelled | Difference |
| --- | --- | --- | --- | --- | --- |

## Make it yours

1. Copy the complete **Health Evidence** folder to your own workspace and add the copy to Flow.
2. Open [[Health Evidence Settings]], choose **View ▸ Edit Table**, and change the **Settings** value for `review_threshold_pct` from **6 to 8**. Save the input. Run the jobs with the moon's **Run now** action.
3. Expect **Weeks above the threshold** to change from **5 to 1**. The six observed rates and the pooled 7.2% remain unchanged; changing a threshold cannot change the evidence.
4. Replace both fictional snapshot files and the source notes with non-identifying aggregates you are authorized to use. Keep the outcome definitions and denominators explicit. The latest dated snapshot supplies the complete series.
5. Open [[Health Evidence Refresh]], then choose **File ▸ Edit Definition…**. Return here and use **File ▸ Night Shift Jobs…** to adjust the source watch when adding local folders. Enable Night Shift if you want scheduled updates.

## Optional overnight notes

The saved jobs collect local data and watch source changes. They do not need a model. To add a short interpretation, use **File ▸ Night Shift Jobs…** on this document and add **Overnight notes** after configuring a local Night model. Read the proposed notes against the inputs; an interpretation is not another source. Nothing is sent or published by this workspace.

<!-- night: notes -->
<!-- /night: notes -->
