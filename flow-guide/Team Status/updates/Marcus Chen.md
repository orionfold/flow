---
title: Marcus Chen
tags: [status, update]
---
# Marcus Chen

**Illustrative business record.**

## Record

| name | area | status | confidence | updated | this_week | next_week | blocker |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Marcus Chen | Search | amber | 60 | 2026-08-31 | Rebuilt the index writer; the rebuild on the 40,000-note vault is at 48 s, target is 30 s. | Profile the tokenizer, which is 60% of the time, and try the batched write. | Need the perf fixture from Platform before the batched write can be measured honestly. |

## About these inputs

Choose **View ▸ Edit Table** to edit this record, then save the document. Keep one record in this table; copy the whole document when adding another person or form.

One file per person, rewritten each week. The Record table is what rolls up into [[Team Status]] every night: name, area, a traffic-light status, a confidence number, and the three sentences.

| Field | Meaning |
| --- | --- |
| `status` | `green` on track, `amber` at risk, `red` blocked or slipping |
| `confidence` | 0 to 100: how sure you are the area lands on the plan |
| `updated` | The date you last rewrote this file |
| `this_week`, `next_week`, `blocker` | One sentence each; keep them under a line |

## Notes

- Two of the three slow queries are the same shape: a prefix over a deleted note.
- Holding the release note until the 30 s target is met or explicitly waived.
