---
title: Portugal Itinerary
category: personal-money
summary: "Itinerary, reservations to check and a travel budget."
tags: ["travel-planner", "example"]
jobs:
  - kind: gather
    definition: Travel Refresh.md
    as: review
  - kind: keep-sources-fresh
    watch: ["Travel Plan.md"]
  - kind: overnight-notes
---
# Portugal Itinerary

**8–18 October 2026 · two travellers · fictional plan · 10 nights**

![Terracotta rooftops and blue-tiled facades above an imagined Portuguese river at sunset](assets/portugal-river.png)

*An original travel illustration; not a route map or a photograph of a booked stay.*

## Five stops, with one night left deliberately open

Start with three nights in Lisbon, continue north through Óbidos and Coimbra, then spend three nights in Porto. Keep the Douro night as a shortlist until transport and cancellation terms are clear.

<!-- data: data/review-*.json#stays -->
| Place | Arrival | Departure | Nights | Budget EUR | Status |
| --- | --- | --- | --- | --- | --- |
| Lisbon | 2026-10-08 | 2026-10-11 | 3 | 420 | Planned |
| Óbidos | 2026-10-11 | 2026-10-12 | 1 | 160 | Planned |
| Coimbra | 2026-10-12 | 2026-10-14 | 2 | 190 | Planned |
| Porto | 2026-10-14 | 2026-10-17 | 3 | 480 | Planned |
| Douro Valley | 2026-10-17 | 2026-10-18 | 1 | 210 | Shortlist |

## A budget you can revise

```chart data: data/review-*.json#budget
chartType: Donut Chart
baseSize: {width: 640, height: 300}
title: The trip budget by purpose
subtitle: Planned EUR · two travellers
source: Fictional bundled example; replace with your own records
data:
  - {category: "Accommodation", amount: 1460}
  - {category: "Flights", amount: 640}
  - {category: "Food", amount: 700}
  - {category: "Transport", amount: 400}
  - {category: "Activities and contingency", amount: 300}
semantic_types:
  category: Category
  amount: Amount
encodings:
  size:
    field: amount
  color:
    field: category
    scheme: oranges
```

<!-- data: data/review-*.json#summary -->
| Metric | Value |
| --- | ---: |
| Nights | 10 |
| Accommodation, EUR | 1460 |
| Total budget, EUR | 3500 |

Accommodation comes from the stay rows; the other allowances come from [[Travel Plan]]. Both update this budget when Gather runs. These are planned totals for the two travellers, not current fares or per-person daily quotes.

## Before anything is booked

- [ ] Confirm the dates, travellers and actual availability.
- [ ] Record cancellation and check-in terms for each stay.
- [ ] Choose transport only after comparing the actual route and total cost.
- [ ] Put any time-sensitive admission or timetable checks in a dated note.

This folder plans the work; it does not make reservations.
## Make it yours

1. Copy this entire folder in Finder, give the copy a name, then choose **Add Folder** in Flow. Keep its local subfolders beside the documents.
2. Open **Travel Plan** and choose **View ▸ Edit Table** to replace the fictional records. Keep the column names and edit the cells, then save. The saved definition controls the calculation; the living report’s Jobs control recurring work.
3. Change Porto’s stay budget from 480 to 510. Gather should change accommodation from **€1,460 to €1,490**. The donut should update with it, and the total should become **€3,530**. Replace the other allowances with your own checked estimates.
4. With this document open, choose **File ▸ Night Shift Jobs…** to review its saved work; save any changes and close the editor. Choose **Settings ▸ Night Shift ▸ Run now**, then inspect the changed table or chart and the Briefing. Gather uses local calculations; optional Overnight notes need a configured local model. Enable Night Shift only for scheduled runs.
5. Replace the illustrative prose with your own assessment after checking the inputs. A chart can refresh its numbers; it cannot certify the conclusions around it.


## Review notes

Keep your decision here. Optional Night Shift notes appear below after a configured local model runs.

<!-- night: notes -->
<!-- /night: notes -->
