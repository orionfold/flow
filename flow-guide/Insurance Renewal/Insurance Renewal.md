---
title: Insurance Renewal
tags: [insurance, operations, living-workspace, fictional-example]
jobs:
  - kind: gather
    definition: Insurance Renewal Refresh.md
    into: data
    as: insurance-renewal
  - kind: keep-sources-fresh
    watch: [Insurance Renewal Settings.md, inputs, sources]
---
# Insurance Renewal

A renewal meeting is useful when the facts are already in order. This desk brings together Alder Design Studio's expiring premiums, quotations, preparation dates, and missing documents. The sample's open question is why one quotation changed—not which policy to buy.

> **Fictional working example.** Annual prices are USD. Source notes support the figures; policy wording and coverage advice remain with the broker.

<!-- data: data/insurance-renewal-*.json#review -->
| Business | As of | Period |
| --- | --- | --- |
| Alder Design Studio | 2026-09-12 | 2026 renewal |

## Put the missing documents first

<!-- data: data/insurance-renewal-*.json#outstanding -->
| Item | Owner | Status | Source id |
| --- | --- | --- | --- |
| Professional liability full quote forms | Nina Park | requested | IR-02 |
| Cyber renewal quotation | Jon Bell | requested | IR-03 |

## Compare the quoted prices without hiding the gap

The change is relative to each expiring annual premium. **Pending is not zero.** The two available prices are not evidence that the contracts offer equivalent protection.

<!-- data: data/insurance-renewal-*.json#comparison -->
| Policy | Current amount | Offer | Change | Change pct | Renewal | Source id |
| --- | --- | --- | --- | --- | --- | --- |
| Business owners | 3500 | 3710 | 210 | 6 | 2026-10-01 | IR-01 |
| Professional liability | 4200 | 4620 | 420 | 10 | 2026-10-15 | IR-02 |
| Cyber | 1800 | Pending | Pending | Pending | 2026-11-01 | IR-03 |

Read the [12 September revision](sources/Insurance%20Packet%20%E2%80%94%202026-09-12.md) beside the [original packet](sources/Insurance%20Packet%20%E2%80%94%202026-09-05.md): the professional-liability quotation increased by USD 140, while its current premium did not change. Ask for the reason and the full terms before drawing a conclusion.

## Leave time for the conversation

These are team preparation windows, not policy periods or legal deadlines.

```chart data: data/insurance-renewal-*.json#timeline
chartType: Gantt Chart
title: "Preparation windows before the renewal conversations"
subtitle: "September–October 2026 · fictional team plan"
source: "Newest insurance snapshot; team-authored start and due dates"
data:
  - {task: "Business owners review", start: "2026-09-08", due: "2026-09-22", stage: "Review packet"}
  - {task: "Professional liability review", start: "2026-09-15", due: "2026-10-01", stage: "Review packet"}
  - {task: "Cyber information request", start: "2026-09-22", due: "2026-10-08", stage: "Gather information"}
semantic_types: {"task": "Name", "start": "Date", "due": "Date", "stage": "Category"}
encodings:
  y: {"field": "task"}
  x: {"field": "start"}
  x2: {"field": "due"}
  color: {"field": "stage", "scheme": "oranges"}
```

## Bring three questions to the broker

1. What explains the revised professional-liability price, and did any terms change?
2. Which full forms are still missing from the packet?
3. When can the outstanding cyber quotation be supplied?

[[Insurance Renewal Sources]] distinguishes supplied facts from the questions they leave open.

## Make it yours

1. Copy this entire **Insurance Renewal** folder in Finder to your own workspace and add that folder to Flow. Work in the copy.
2. Open [[insurance-snapshot-2026-09-12]] and use the **Policies** table's **Open in the table editor** control. Change the professional-liability `quote_amount` from **4620 to 4500**; leave `current_amount` at 4200, then save. [[Insurance Renewal Settings]] selects the policy year.
3. Use the moon's **Run now** action. The Gather job runs [[Insurance Renewal Refresh]]. Expect the professional-liability row to show **4500 offered, 300 change, 7.1 change pct**. The cyber offer stays Pending.
4. Replace the fictional source notes and snapshots with your own complete packet. Keep filenames dated `YYYY-MM-DD`; the newest matching snapshot wins. Keep all essentials inside the copied folder.
5. Use **File ▸ Night Shift Jobs…** here for the source watch. For calculation changes, open [[Insurance Renewal Refresh]], then choose **File ▸ Edit Definition…**. Automatic nights require Night Shift to be enabled; otherwise run the jobs when needed.

The tables and chart redraw from captures. Your surrounding prose and questions stay authored; revise them when the evidence changes.

## Optional overnight notes

The saved jobs collect local data and watch source changes. They do not need a model. To add a short interpretation, use **File ▸ Night Shift Jobs…** on this document and add **Overnight notes** after configuring a local Night model. Read the proposed notes against the inputs; an interpretation is not another source. Nothing is sent or published by this workspace.

<!-- night: notes -->
<!-- /night: notes -->
