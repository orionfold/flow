---
title: Profile
tags: [starter, parameters, night-shift]
subject: The thing this document keeps current
owner: Your name
items:
  - {name: First item, group: A, amount: 120, start: 2026-09-01, due: 2026-09-15, status: open}
  - {name: Second item, group: A, amount: 80, start: 2026-09-08, due: 2026-09-22, status: in progress}
  - {name: Third item, group: B, amount: 200, start: 2026-08-18, due: 2026-09-01, status: done}
---
# Profile

The one file you edit. Everything in the front matter above is read by
[[Living Document]] each night: the scalars at the top can fill a key-value
table, and `items` is a list the tables and charts draw from. Rename the
keys to your domain; keep the shape.

## The shape the night reads

| Shape | Example | What it becomes |
| --- | --- | --- |
| A scalar at the top level | `owner: Your name` | One row of a key-value table bound to `Profile.md` with no `#key` |
| A list of flow maps | `- {name: …, amount: 120}` | One row per line in a table or chart bound to `Profile.md#items` |
| A quoted string | `note: "Ship, then measure"` | A value that contains a comma or a colon must be quoted, or it splits |
| A number | `amount: 120` | Drawn as a number; kept exactly as you spelled it |
| A date | `start: 2026-09-01` | Drawn on a time axis when the chart's `semantic_types` says `Date` |

## Make it yours

1. Replace `subject` and `owner`.
2. Rename the keys in `items` to the columns your domain has, and put your
   real rows in.
3. In [[Living Document]], change the table headers and the chart's
   `encodings` to the new key names. Headers match keys in any case.
