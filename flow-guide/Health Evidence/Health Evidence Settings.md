---
title: Health Evidence Settings
tags: [health, settings, fictional-example]
---
# Health Evidence Settings

**Illustrative business inputs.** Edit the named table using its **Open in the table editor** control. **View ▸ Edit Table** opens the first table. Save the input document, then run the Jobs on [[Health Evidence]]; its refreshed views read these saved rows.

## Settings

| key | value |
| --- | --- |
| team | Maple Grove clinic operations |
| owner | Samira Ellis |
| review_threshold_pct | 6 |

## About these inputs

The fictional operations team tracks appointments that did not take place. `review_threshold_pct` is a team-selected prompt for discussion, not a clinical standard, medical recommendation, or published benchmark.

## The denominator stays visible

Each row represents one week's scheduled appointments in one fictional service. Every appointment must fall into exactly one of three outcomes: completed, missed without cancellation, or cancelled before the appointment. There is no patient-level information.

`scheduled = completed + missed + cancelled`

The missed percentage is `missed / scheduled × 100`. A zero scheduled count displays **No denominator**, never a false 0%. Totals use the combined numerator and denominator; the refresh does not average weekly percentages.

The source watch includes `inputs/` and `sources/`. Add a new complete snapshot with a later `YYYY-MM-DD` filename; do not append a second copy of the same week. The latest matching snapshot supplies the whole series.

| Field | Sample or rule | Effect |
| --- | --- | --- |
| `review_threshold_pct` | 6 | Counts weeks whose missed share is strictly above 6% |
| `scheduled` | Completed + missed + cancelled | Denominator for the weekly missed share |
| Packet filename date | Latest complete snapshot | Selects the whole series; older snapshots are not added again |
| Zero scheduled appointments | No denominator | Leaves the rate unavailable |

The threshold is used only for the count of weeks to review. Changing it does not change observed appointment totals or rates.
