---
title: Living Document
category: learn-flow
summary: "Your own small recurring project, with the smallest useful Jobs."
tags: [starter, dashboard, night-shift]
jobs:
  - kind: gather
    definition: Starter Refresh.md
  - kind: keep-sources-fresh
    watch: [Profile.md, entries]
  - kind: reconcile-against-folder
    folder: entries
  - kind: overnight-notes
---
# Living Document

**Keep a small project review ready without rebuilding the same report.** This starter turns one plan and one source note into a useful weekly pulse.

> Fictional onboarding study · as of 2 September 2026 · effort in planned minutes. Group A is Discovery; group B is Delivery.

**Supplied snapshot · 2 September 2026:** the plan allocates 400 of 500 available minutes across three items, with two still open. The pulse below follows your current inputs; review this authored summary after changing them. **Next action:** confirm who will attend the prototype review before adding more work. Planned effort is not time spent, and a completed inventory is not evidence that an interview happened.

[[Profile]] owns the items and capacity target. [[Starter Refresh]] computes the count and total. The note in `entries/` supplies context for Search and optional local-model Overnight notes.

## The pulse

```chart data: data/capture-*.json#summary
chartType: KPI Card
title: Open work and planned capacity
subtitle: Fictional project; target belongs to Profile
source: data/capture-*.json
data:
  - {metric: "Items", value: 3}
  - {metric: "Open items", value: 2}
  - {metric: "Planned minutes", value: 400, goal: 500}
semantic_types: {metric: Category, value: Quantity, goal: Quantity}
encodings:
  metric: {field: metric}
  value: {field: value}
  goal: {field: goal}
```

## Work that earns its place in the plan

<!-- data: Profile.md#table:Items -->
| Name | Group | Amount | Start | Due | Status |
| --- | --- | ---: | --- | --- | --- |
| Peer interviews | A | 120 | 2026-09-01 | 2026-09-15 | open |
| Prototype review | A | 80 | 2026-09-08 | 2026-09-22 | in progress |
| Source inventory | B | 200 | 2026-08-18 | 2026-09-01 | done |

```chart data: Profile.md#table:Items
chartType: Bar Chart
title: Planned effort by work item
subtitle: Minutes; A is Discovery, B is Delivery
source: Profile.md, Items table
data:
  - {name: "Peer interviews", group: "A", amount: 120, start: "2026-09-01", due: "2026-09-15", status: "open"}
  - {name: "Prototype review", group: "A", amount: 80, start: "2026-09-08", due: "2026-09-22", status: "in progress"}
  - {name: "Source inventory", group: "B", amount: 200, start: "2026-08-18", due: "2026-09-01", status: "done"}
semantic_types: {name: Category, amount: Amount, group: Category}
encodings:
  y: {field: name}
  x: {field: amount}
  color: {field: group, scheme: purples}
```


## Context on file

[[Example Entry]] records the unresolved participant question. Keep notes, source documents and essential images inside this folder when adapting the starter. A source note can explain a number; it does not make that number measured.

## Source inventory

```flow-folder entries
| File | Size | Modified | Digest |
| --- | ---: | --- | --- |
| Example Entry.md | 755 |  |  |
```

Bundled file list; the inventory job fills timestamps and digests in your working copy.

## Make it yours

1. Copy the whole **Living Document Starter** folder, name it for your project and add it in Flow. The local profile, definition, entries and saved capture travel together.
2. Open [[Profile]] and choose **View ▸ Edit Table**. In **Items**, change Peer interviews from 120 to 150 minutes, then save. After a completed run, the planned total should become 430 while the 500-minute capacity and three-item count remain unchanged.
3. Replace the fictional owner, rows and [[Example Entry]]. Use the **Settings** table's **Open in the table editor** control to change `planned_minutes` when your capacity changes; there is no second hard-coded target in the definition.
4. Open [[Starter Refresh]], then choose **File ▸ Edit Definition…**. Return to this Living Document and use **File ▸ Night Shift Jobs…** to inspect its saved work. Use the Table and Chart editors to adapt labels and dimensions; the underlying keys remain visible in the source.
5. Choose **Settings ▸ Night Shift ▸ Run now**; scheduling can stay off for this practice run. Check its capture, result and refreshed values. The deterministic Gather is local; optional Overnight notes need a configured local model. No public reads or external writes are required.

## What a run changes

Gather writes the summary; bound views refresh from its capture and the profile. The source-watch and inventory jobs report the files you named. The document text around those bound views remains authored text. Review it when your conclusion changes; automatic refresh does not make a stale conclusion true.

## Overnight notes
<!-- night: notes -->
<!-- /night: notes -->
