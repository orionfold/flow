---
title: Sam Whitaker
tags: [status, update]
name: Sam Whitaker
area: Platform
status: red
confidence: 35
updated: 2026-09-01
this_week: "The signing pipeline broke on the new runner image; two days lost to a certificate that the image no longer trusts."
next_week: "Pin the runner image, then hand Search the perf fixture."
blocker: "The pinned image needs an infra ticket approved; without it every build after Tuesday is unsigned."
---
# Sam Whitaker

One file per person, rewritten each week. The front matter is what rolls up
into [[Team Status]] every night: name, area, a traffic-light status, a
confidence number, and the three sentences.

| Field | Meaning |
| --- | --- |
| `status` | `green` on track, `amber` at risk, `red` blocked or slipping |
| `confidence` | 0 to 100: how sure you are the area lands on the plan |
| `updated` | The date you last rewrote this file |
| `this_week`, `next_week`, `blocker` | One sentence each; keep them under a line |

## Notes

- Root cause: the base image dropped the intermediate CA on 08-28.
- Workaround in place for local builds only.
