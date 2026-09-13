---
title: Sam Whitaker
tags: [status, update]
---
# Sam Whitaker

**Illustrative business record.**

## Record

| name | area | status | confidence | updated | this_week | next_week | blocker |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Sam Whitaker | Platform | red | 35 | 2026-09-01 | The signing pipeline broke on the new runner image; two days lost to a certificate that the image no longer trusts. | Pin the runner image, then hand Search the perf fixture. | The pinned image needs an infra ticket approved; without it every build after Tuesday is unsigned. |

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

- Root cause: the base image dropped the intermediate CA on 08-28.
- Workaround in place for local builds only.
