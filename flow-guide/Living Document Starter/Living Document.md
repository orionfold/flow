---
title: Living Document
tags: [starter, dashboard, night-shift]
jobs:
  - kind: gather
    definition: Starter Refresh.md
  - kind: keep-sources-fresh
    watch: [Profile.md, entries, https://orionfold.com/flow/]
  - kind: reconcile-against-folder
    folder: entries
  - kind: overnight-notes
---
# Living Document

Copy this folder, rename it for your domain, and edit three things: the
front matter of [[Profile]], the files in `entries/`, and the headers and
titles below. Every construct the Night Shift can keep current is wired
here exactly once, with a note on where it reads from. Delete the ones you
do not need.

The `jobs:` block above is what makes this a living document. `watch`
names the files, folders and public pages the night compares with the night
before; `folder` names the folder the night inventories; `refresh-from-data`
redraws every block bound to a file. Nothing else creates a job.

## A key-value table from the profile's scalars

Bound to `Profile.md` with no `#key`: every scalar at the top of the front
matter, one row each.

<!-- data: Profile.md -->
| | |
| --- | --- |
| title | Profile |
| subject | The thing this document keeps current |
| owner | Your name |

## A table from a list

Bound to `Profile.md#items`. The header names the columns to draw, in the
order you want them, matched to the keys in any case.

<!-- data: Profile.md#items -->
| Name | Group | Amount | Start | Due | Status |
| --- | --- | ---: | --- | --- | --- |
| First item | A | 120 | 2026-09-01 | 2026-09-15 | open |
| Second item | A | 80 | 2026-09-08 | 2026-09-22 | in progress |
| Third item | B | 200 | 2026-08-18 | 2026-09-01 | done |

## A chart from the same list

The same binding on a chart opener. The night rewrites only the `data:`
rows; the chart type, title and encodings are yours. Change `x`, `y` and
`color` to your key names.

```chart data: Profile.md#items
chartType: Bar Chart
title: Amount by item
subtitle: From Profile.md
source: Profile.md, front matter
data:
  - {name: "First item", group: "A", amount: 120, start: "2026-09-01", due: "2026-09-15", status: "open"}
  - {name: "Second item", group: "A", amount: 80, start: "2026-09-08", due: "2026-09-22", status: "in progress"}
  - {name: "Third item", group: "B", amount: 200, start: "2026-08-18", due: "2026-09-01", status: "done"}
semantic_types: {name: Category, amount: Amount, group: Category}
encodings:
  y: {field: name}
  x: {field: amount}
  color: {field: group}
```

## A timeline from dates in the list

A Gantt reads two date keys, `start` and `due`, as its ends and any key as
its colour.

```chart data: Profile.md#items
chartType: Gantt Chart
title: Items by due date
subtitle: From Profile.md
source: Profile.md, front matter
data:
  - {name: "First item", group: "A", amount: 120, start: "2026-09-01", due: "2026-09-15", status: "open"}
  - {name: "Second item", group: "A", amount: 80, start: "2026-09-08", due: "2026-09-22", status: "in progress"}
  - {name: "Third item", group: "B", amount: 200, start: "2026-08-18", due: "2026-09-01", status: "done"}
semantic_types: {name: Name, start: Date, due: Date, status: Category}
encodings:
  y: {field: name}
  x: {field: start}
  x2: {field: due}
  color: {field: status}
```

## One row per file in a folder

Bound to `entries/*.md` with no `#key`: one row per file, from that file's
front matter. This is the pattern for anything owned by many people.

<!-- data: entries/*.md -->
| name | group | score | updated | note |
| --- | --- | ---: | --- | --- |
| Example Entry | A | 72 | 2026-09-02 | One file per thing; the night reads each file's front matter as one row. |

## A chart from a data capture

Bound to `data/capture-*.json#summary`: the star takes the newest file by
name, the key takes the list inside it. [[Starter Refresh]] writes the file:
it is a gather definition, a document naming where each figure comes from and
how it is shaped. Flow reads it before it redraws. Edit it to describe what
your own document needs.

```chart data: data/capture-*.json#summary
chartType: KPI Card
title: The numbers at a glance
subtitle: From the newest capture
source: data/capture-*.json
data:
  - {metric: "Items", value: 3}
  - {metric: "Open items", value: 2}
  - {metric: "Total amount", value: 400, goal: 500}
semantic_types: {metric: Category, value: Quantity, goal: Quantity}
encodings:
  metric: {field: metric}
  value: {field: value}
  goal: {field: goal}
```

```chart data: data/capture-*.json#byGroup
chartType: Donut Chart
title: Amount by group
subtitle: From the newest capture
source: data/capture-*.json
data:
  - {group: "A", amount: 200}
  - {group: "B", amount: 200}
semantic_types: {group: Category, amount: Amount}
encodings:
  size: {field: amount}
  color: {field: group}
```

## The folder's inventory

The `reconcile-against-folder` job keeps this fence current: name, size,
modified date and a short digest, one row per file.

```flow-folder entries
| File | Size | Modified | Digest |
| --- | ---: | --- | --- |
| Example Entry.md | 687 | 2026-09-03T05:11:19Z | 8742c9f9cb40 |
```

## What you will see in the morning

- **You edited the profile.** The tables and charts bound to it are current,
  and the Briefing shows the exact diff of the file.
- **A file landed in `entries/`.** The inventory names it and the
  one-row-per-file table has its row.
- **A watched page changed.** The Briefing shows the text that changed.
- **The refresh wrote a capture.** The blocks bound to `data/` redrew from it.
- **Nothing moved.** An honest empty morning, and the run is in Receipts.

## Make it yours

1. Duplicate this folder in Finder and name it for the thing it keeps
   current. Inside the Guide or anywhere you Add Folder; paths are relative
   to this document, so the folder moves as one piece.
2. Edit [[Profile]]: your keys, your rows. Quote any value with a comma.
3. Rename the headers and the chart `encodings` above to your keys, retitle
   the charts, delete the blocks you do not need.
4. Put the pages you want watched in `watch`; public `https` only, each
   fetch has a receipt. Remove the example page.
5. If you need fetched or computed data, edit [[Starter Refresh]] to name
   your source and the shape you want back; the `gather` job above reads it
   before every redraw. Nothing runs, so there is nothing to allow. If you
   do not need it, delete the `gather` job, [[Starter Refresh]] and `data/`,
   and the two capture-bound charts above.
6. Turn the Night Shift on: the moon in the title bar, or Settings ▸ Night
   Shift. The first shift runs while you watch.

## How this page is built

| Block | Construct | Bound to | Redrawn by |
| --- | --- | --- | --- |
| Key-value table | table under a `data:` comment | `Profile.md` | the night alone |
| Table from a list, bar chart, timeline | table and charts | `Profile.md#items` | the night alone |
| One row per file | table over a glob | `entries/*.md` | the night alone |
| KPI card, donut | charts | `data/capture-*.json#summary`, `#byGroup` | refresh, then the night |
| Inventory | `flow-folder` fence | `entries/` | the night alone |
| Watched page | `watch` in the `jobs:` block | one public page | the night alone |

The rules in one breath: a binding is a path relative to this document; a
`*` takes the newest file by name; `#key` names the list inside a JSON file
or a Markdown file's front matter; a glob with no key reads one row per
file; the night rewrites rows only and never the text around them.

## Overnight notes
<!-- night: notes -->
<!-- /night: notes -->
