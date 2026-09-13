---
title: Business Review
tags: ["business-review", "example"]
jobs:
  - kind: gather
    definition: Business Review Refresh.md
    as: review
  - kind: keep-sources-fresh
    watch: ["Quarterly Close.md", "Decision Record.md"]
  - kind: overnight-notes
---
# Business Review

**Meridian Software · FY2026 review · fictional full-year scenario**

## Growth is healthy; the next decision is how to sustain it

Revenue reaches **$19.2M**, up **34.3%** from the sample prior-year $14.3M. The second half supplies **56.8%** of revenue and all the operating profit. Approve the next plan only after the team explains the new-customer and self-serve risks in [[Decision Record]].

```chart data: data/review-*.json#quarters
chartType: Line Chart
title: Revenue grew in every quarter
subtitle: USD millions · recognised revenue · FY2026
source: Fictional bundled example; replace with your own records
data:
  - {series: "Revenue", quarter: "Q1", revenue_m: 3.9, gross_margin_pct: 79, customers: 404, operating_income_m: -0.4}
  - {series: "Revenue", quarter: "Q2", revenue_m: 4.4, gross_margin_pct: 80, customers: 419, operating_income_m: -0.2}
  - {series: "Revenue", quarter: "Q3", revenue_m: 5.2, gross_margin_pct: 82, customers: 433, operating_income_m: 0.3}
  - {series: "Revenue", quarter: "Q4", revenue_m: 5.7, gross_margin_pct: 83, customers: 447, operating_income_m: 0.7}
semantic_types:
  quarter: Category
  revenue_m: Amount
encodings:
  x:
    field: quarter
  y:
    field: revenue_m
  color:
    field: series
    scheme: teals
```

<!-- data: data/review-*.json#summary -->
| Metric | Value |
| --- | --- |
| Revenue, $M | 19.2 |
| Operating income, $M | 0.4 |
| Gross margin, % | 81.2 |

## The review pack

| Document | Question |
| --- | --- |
| [[Annual Review]] | What changed, and what did we learn? |
| [[Revenue Detail]] | How do the quarter totals reconcile? |
| [[Quarterly Review]] | Which Q3 signal needs action? |
| [[Shareholder Letter]] | How do we explain performance to owners? |
| [[Decision Record]] | What did we decide, and what would change our mind? |
| [[Team Working Agreement]] | How does the team keep this record useful? |

## Make it yours

1. Copy this entire folder in Finder, give the copy a name, then choose **Add Folder** in Flow. Keep its local subfolders beside the documents.
2. Open [[Quarterly Close]] and choose **View ▸ Edit Table** to change the **Quarters** records. Keep the column names and edit the cells, then save. Open [[Business Review Refresh]] in Definition editing if you want to change the calculation.
3. Try changing Q4 revenue from 5.7 to 6.0. The refreshed annual total should become **$19.5M**; then review every authored conclusion that depends on it.
4. With this document open, choose **File ▸ Night Shift Jobs…** to review its saved work; save any changes and close the editor. Choose **Settings ▸ Night Shift ▸ Run now**, then inspect the changed table or chart and the Briefing. Gather uses local calculations; optional Overnight notes need a configured local model. Enable Night Shift only for scheduled runs.
5. Replace the illustrative prose with your own assessment after checking the inputs. A chart can refresh its numbers; it cannot certify the conclusions around it.


## Review notes

Keep your decision here. Optional Night Shift notes appear below after a configured local model runs.

<!-- night: notes -->
<!-- /night: notes -->
