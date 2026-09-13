---
title: Charts — Living Example
tags: [charts-gallery, living-workspace, fictional-example]
jobs:
  - kind: gather
    definition: Gallery Refresh.md
    into: data
    as: gallery
  - kind: keep-sources-fresh
    watch: [Gallery Data.md]
---
# Charts — Living Example

[[Charts Gallery]] · Input: [[Gallery Data]] · Next: [[Charts — Comparisons]]

**One source, two questions.** The same planned hours answer “how much for each activity?” in a bar chart and “what share of this plan?” in a donut. Compare the views before choosing one for your own document.

> Fictional planning exercise · as of 12 September 2026 · hours. These are authored estimates, not work completed or productivity measurements.

## Compare the amounts

```chart data: data/gallery-*.json#records
chartType: Bar Chart
title: Planned hours by activity
subtitle: Hours; one shared baseline
source: Newest gallery capture from Gallery Data; fictional plan
data:
  - {activity: "Research", hours: 8}
  - {activity: "Writing", hours: 6}
  - {activity: "Review", hours: 4}
  - {activity: "Planning", hours: 2}
semantic_types: {activity: Category, hours: Quantity}
encodings:
  y: {field: activity}
  x: {field: hours}
  color: {field: activity, scheme: tableau10}
```

Use the bar chart to compare exact amounts and small differences. Category colours have the same meaning in the donut below.

## See the parts of this plan

```chart data: data/gallery-*.json#records
chartType: Donut Chart
title: Each activity's share of the entered plan
subtitle: Hours; all four rows form the supplied whole
source: Newest gallery capture from Gallery Data; fictional plan
data:
  - {activity: "Research", hours: 8}
  - {activity: "Writing", hours: 6}
  - {activity: "Review", hours: 4}
  - {activity: "Planning", hours: 2}
semantic_types: {activity: Category, hours: Quantity}
encodings:
  size: {field: hours}
  color: {field: activity, scheme: tableau10}
```

A share changes when its numerator or the total changes. After the practice edit, Review occupies 7 of 23 hours, about 30.4%; it is not 35% of the old 20-hour plan. This paragraph is an authored worked example, not a generated result.

<!-- data: data/gallery-*.json#summary -->
| Metric | Value |
| --- | ---: |
| Planned hours | 20 |
| Activities | 4 |

## Make it yours

1. Copy the complete **Charts Gallery** folder and add the copy to Flow. Work in that copy.
2. Open [[Gallery Data]] and use **View ▸ Edit Table** on its Records table. Change Review from **4 to 7** hours and save.
3. Return here and choose **Settings ▸ Night Shift ▸ Run now**. Scheduling can stay off. Expect Review's bar to show **7**, its donut share to become **7 of 23**, and the summary to show **23 planned hours and four activities**. Review the Briefing and changed document.
4. Replace the fictional activity rows with your own complete plan. Keep the Records heading and both columns; update the date, labels and authored explanation when their meaning changes. Use nonnegative hours and a positive total for the donut.
5. Open [[Gallery Refresh]], then choose **File ▸ Edit Definition…** to inspect the total. Return here and use **File ▸ Night Shift Jobs…** to review the Gather job and source watch. There are no public reads, model calls or writes to another system.

## What refresh changes

Gather reads the saved source table and writes its rows and summary to one capture. Both charts and the summary table redraw from that newest matching capture. Your source rows and this explanation remain authored. The static examples on the category pages have separate embedded data and do not change when you edit this practice plan.

Automatic local redraw may run as data changes when that setting is on. Run now gives you an explicit refresh without enabling an overnight schedule. A failed run is not evidence that the saved visual is current.

Back: [[Charts Gallery]] · Input: [[Gallery Data]] · Definition: [[Gallery Refresh]] · Next: [[Charts — Comparisons]]
