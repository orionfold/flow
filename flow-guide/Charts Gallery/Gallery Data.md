---
title: Gallery Data
tags: [charts-gallery, input, fictional-example]
---
# Gallery Data

[[Charts Gallery]] · [[Charts — Living Example]]

**A fictional half-week work plan, as of 12 September 2026.** These are planned hours, not time tracking or measured productivity. The table below is the one editable source for the living example.

## Records

| activity | hours |
| --- | ---: |
| Research | 8 |
| Writing | 6 |
| Review | 4 |
| Planning | 2 |

## Edit the input, then inspect the result

Use **View ▸ Edit Table** on this document, change Review's hours from 4 to 7 and save. Open [[Charts — Living Example]] and choose **Settings ▸ Night Shift ▸ Run now**. The total becomes 23 hours; the four activity names stay the same. If redraw-as-data-changes is enabled, the local views may already have refreshed; the manual run remains an explicit check.

Keep the heading **Records** and one table beneath it. Keep `activity` and `hours` as the column names, one nonblank activity per row and finite, nonnegative numeric hours. The donut requires a positive total. Remove example rows when adding your real plan; otherwise both sets will be counted. A zero is an entered zero, not a placeholder for an unknown amount.

The source table is authored input. It has no data-binding comment above it and is not overwritten by the refresh. If you rename the heading, update the source in [[Gallery Refresh]]. If you rename a field, update the definition and the chart encodings in [[Charts — Living Example]] together.

Back: [[Charts Gallery]] · Next: [[Charts — Living Example]]
