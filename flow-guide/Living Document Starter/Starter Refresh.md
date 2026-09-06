---
title: Starter Refresh
tags: [starter, definition, night-shift]
sources:
  items: Profile.md#items
let:
  count: {count: items, of: items}
  open: {count: items, of: items, where: "status != 'done'"}
  total: {sum: amount, of: items}
emit:
  summary:
    - {metric: Items, value: "{count}"}
    - {metric: Open items, value: "{open}"}
    - {metric: Total amount, value: "{round(total, 0)}", goal: 500}
  byGroup:
    from: items
    steps:
      - {aggregate: group, sum: amount, as: amount}
      - {calculate: "round(amount, 0)", as: amount}
      - {sort: group}
---
# How this document refreshes itself

This is the definition [[Living Document]] runs each night. It is **data, not
code** — every line is something you can read and change, and Flow runs it
itself rather than running a program. Nothing here can reach outside this
folder or do anything but read, work out and write the capture.

Three parts, in the order the night reads them.

## `sources:` — what to read

One name per source. `items` reads the `items` list out of [[Profile]]'s
front matter, which is what `Profile.md#items` means: the file, then the key
inside it.

A source can also be a file pattern (`statements/*.csv` reads every matching
file as one set of rows), a folder of notes (`inputs/*.md` reads each one's
front matter), or a web address you write down.

## `let:` — what to work out

Named values, computed in the order you write them. Each one may use any
value written above it and none written below, so there is never a question
of what depends on what.

`{count: items, of: items}` counts the rows. `{sum: amount, of: items}` adds
up the `amount` column. Adding `where:` counts or adds only the rows that
match — here, the ones whose `status` is not `done`.

## `emit:` — what to build

One named table per block your document draws. The name is the `#key` the
block binds to, so `summary` here is what
`<!-- data: data/capture-*.json#summary -->` shows.

A table is written one of two ways:

- **A list of rows**, like `summary`, when you are laying out values you
  worked out above. Anything in `{braces}` is worked out; anything else is
  written as you typed it, which is how `goal: 500` gets there.
- **A pipeline**, like `byGroup`, when you are reshaping rows you gathered.
  It says which source to draw `from` and then the `steps` to run over it, in
  order: group and total, round, sort.

## The steps a pipeline can take

Each one is a line under `steps:`, and they run in the order you write them.

| Step | What it does | Written like |
| --- | --- | --- |
| `filter` | Keeps the rows that match | `- {filter: "amount < 0"}` |
| `calculate` | Adds or replaces a column | `- {calculate: "-amount", as: spent}` |
| `aggregate` | One row per group, with totals | `- {aggregate: category, sum: spent, as: spent}` |
| `window` | A running total or moving average | `- {window: "", sum: spent, as: running}` |
| `joinaggregate` | The group's total on every row of it | `- {joinaggregate: category, sum: spent, as: total}` |
| `lookup` | Brings columns across from another source | `- {lookup: symbol, from: prices, on: ticker}` |
| `rules` | Labels a row by the first matching word | `- {rules: description, as: category, using: rules}` |
| `timeunit` | A date column made coarser | `- {timeunit: date, unit: month, as: month}` |
| `sort` | Orders the rows | `- {sort: spent, descending: true}` |
| `sample` | Keeps the first or last few | `- {sample: 12}` |
| `impute` | Fills a gap in a series | `- {impute: close, key: day, by: [symbol]}` |
| `fold` / `pivot` | Turns columns into rows, and back | `- {fold: [open, close]}` |

## Making it yours

Change `Profile.md#items` to whatever you keep your own data in, rename the
values under `let:`, and rename the tables under `emit:` to match the `#key`
your blocks bind to. The night does the rest.

You need not edit the lines above by hand. The *Definition* line under this
document's title ends in *Edit definition…*, and File ▸ *Edit Definition…*
opens the same editor: each source, value, row set and table as a form,
every step named by what it does, and beside them the rows each step
produces from your files today. A change is written the moment the whole
definition reads; one that does not read yet is held, with the reason shown,
until it does.
