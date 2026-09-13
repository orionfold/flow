---
title: Profile
tags: [starter, parameters, night-shift]
---
# Profile

**Illustrative business inputs.** Edit the named table using its **Open in the table editor** control. **View ▸ Edit Table** opens the first table. Save the input document, then run the Jobs on [[Living Document]]; its refreshed views read these saved rows.

## Items

| name | group | amount | start | due | status |
| --- | --- | --- | --- | --- | --- |
| Peer interviews | A | 120 | 2026-09-01 | 2026-09-15 | open |
| Prototype review | A | 80 | 2026-09-08 | 2026-09-22 | in progress |
| Source inventory | B | 200 | 2026-08-18 | 2026-09-01 | done |

## Settings

| key | value |
| --- | --- |
| subject | Customer onboarding study |
| owner | Alex Morgan |
| planned_minutes | 500 |

## About these inputs

Fictional small project, as of 2 September 2026. `amount` is planned minutes; group A is Discovery and group B is Delivery. `planned_minutes` is the capacity target. The one file you edit. The **Items** table supplies the work records; **Settings** supplies the owner, subject and capacity. Edit their cells in the Table editor and save. Change a column or setting key only when you also update its definition and bound views.

## What the tables mean

| Input | Meaning | Small edit to try |
| --- | --- | --- |
| Items, amount | Planned minutes for one activity | Peer interviews: 120 to 150 |
| Items, group | A is Discovery; B is Delivery | Keep codes consistent when adding a row |
| Settings, planned_minutes | Capacity available to this project | Change the value beside the key |
| Items, start and due | Planned dates, YYYY-MM-DD | Keep dates in this format |

Ordinary edits use the Table editor. Keep the named headings and column names stable so the saved definition can find them. Use title and tag controls for document metadata, and **File ▸ Night Shift Jobs…** on [[Living Document]] for recurring work. Source is an advanced view of the same document.

## Make it yours

1. In **Settings**, edit the `value` cells beside `subject` and `owner`.
2. Replace the sample rows while preserving `name`, `group`, `amount`, `start`, `due` and `status`; keep `amount` in planned minutes unless you update the labels and calculation together.
3. If you need different keys, update the sources, totals, status filter and grouping in [[Starter Refresh]] as well as the table headers and chart encodings in [[Living Document]]. Inspect the definition preview and check an expected total before relying on the renamed fields.
