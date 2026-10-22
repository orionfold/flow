---
title: Client Brief
category: business-teams
summary: "A monthly client brief from the client's own files, every figure sourced, refreshed next month without starting over."
tags: ["client-brief", "example"]
jobs:
  - kind: gather
    definition: Brief Refresh.md
    as: review
  - kind: keep-sources-fresh
    watch: ["Client Figures.md", client-files]
  - kind: reconcile-against-folder
    folder: client-files
  - kind: expand-with-sources
    section: This month
    sources: [client-files, Client Figures.md]
last-updated: 2026-10-18 19:19 · data/review-2026-10-18.json
---
# Client Brief

**Harbour Analytics · fictional monthly brief · September 2026**

![A consultant's desk by a window: notebook, coffee, laptop, morning light](assets/office-desk.jpeg)

Revenue and accounts grew; the support backlog grew faster. The brief below cites the client's own files, which were imported into `client-files/`. The cards, the chart and the table are bound to this month's figures: change a figure in [Client Figures](Client%20Figures.md), **Run Jobs**, and every one of them redraws.

## This month at a glance

```chart data: data/review-*.json#kpis
chartType: KPI Card
title: Three figures the client asks about first
subtitle: September 2026 against the plan the client set
source: Client Figures — Key figures; fictional engagement
data:
  - {metric: "Monthly recurring revenue, $", value: 191500, goal: 200000}
  - {metric: "Active accounts", value: 418, goal: 425}
  - {metric: "Gross margin, %", value: 71, goal: 72}
semantic_types: {metric: Category, value: Quantity, goal: Quantity}
encodings:
  metric: {field: metric}
  value: {field: value}
  goal: {field: goal}
```

## Revenue, six months

```chart data: data/review-*.json#revenue
chartType: Bar Chart
title: Recurring revenue rose every month since April
subtitle: Monthly recurring revenue, $ · April to September 2026
source: Client Figures — Revenue by month; fictional engagement
data:
  - {month: "2026-04", revenue: 171400}
  - {month: "2026-05", revenue: 174900}
  - {month: "2026-06", revenue: 178200}
  - {month: "2026-07", revenue: 181000}
  - {month: "2026-08", revenue: 184000}
  - {month: "2026-09", revenue: 191500}
semantic_types: {month: Category, revenue: Amount}
encodings:
  x: {field: month}
  y: {field: revenue}
```

## What changed since last month

<!-- data: data/review-*.json#changed -->
| Id | Figure | Last month | This month | Source |
| --- | --- | --- | --- | --- |
| F1 | Monthly recurring revenue | $184,000 | $191,500 | Finance workbook |
| F2 | Active accounts | 412 | 418 | Finance workbook |
| F4 | Open support tickets | 38 | 52 | Support export |

## This month

Recurring revenue rose to $191,500 and active accounts to 418. Open support tickets rose from 38 to 52, which the August board deck names as the quarter's top operating risk. **Expand with Sources** can draft this section from the files in `client-files/`; every sentence it proposes cites one, and you keep or revert each change.

## What the brief reads

| File | What it holds | Read by |
| --- | --- | --- |
| [Client Figures](Client%20Figures.md) | This month's figures, with their IDs and sources | The gather job, every run |
| `client-files/Finance Workbook.md` | Revenue, accounts and margin, imported from the workbook | Expand with Sources |
| `client-files/August Board Deck.md` | The board's view of the quarter, imported from the deck | Expand with Sources |

## Next month

Import the new files into `client-files/`, update [Client Figures](Client%20Figures.md), and **Run Jobs**: the cards, the chart and the table above redraw, and the brief shows what changed. **Publish** writes the PDF or Word file the client receives.

## At a glance

Two parts of this brief, side by side — the revenue chart and the figures it rests on — as one block. A block can hold a **Section**, a **Hero** (exactly two, side by side at every width) or a **Bento** (two across, stacked when the column is narrow) of charts, tables, diagrams and checklists; the chart here carries its own values, so a Jobs run leaves it alone and redraws the bound charts above.

```flowui
component: Bento
components:
  - component: Chart
    chart:
      chartType: Bar Chart
      title: Recurring revenue, April to September
      data:
        - {month: "2026-04", revenue: 171400}
        - {month: "2026-05", revenue: 174900}
        - {month: "2026-06", revenue: 178200}
        - {month: "2026-07", revenue: 181000}
        - {month: "2026-08", revenue: 184000}
        - {month: "2026-09", revenue: 191500}
      semantic_types: {month: Category, revenue: Amount}
      encodings:
        x: {field: month}
        y: {field: revenue}
  - component: Table
    title: September against the plan
    rows:
      - {Figure: "Monthly recurring revenue, $", Value: 191500, Plan: 200000}
      - {Figure: Active accounts, Value: 418, Plan: 425}
      - {Figure: Support backlog, Value: 52, Plan: 40}
```

## Acceptance

When the brief is ready, tick what was delivered, type your name and press **Sign off**. Flow shows exactly what it will record, then writes one signed record beside this document — who signed, when, and which items were ticked. The brief's own text does not change, and History shows the signature. If the checklist changes afterwards, the record stays and the card asks for a new signature. **Agency ▸ Sign-off** drafts a checklist like this one from selected text, and the card's **⊟** opens it in the component editor. Ask Chat for an acceptance checklist and it draws the card in its reply before you keep it; the signing still happens here, in the document.

```flowui
component: Approval Card
title: Delivery acceptance · September 2026
subtitle: Harbour Analytics · Brief Refresh of 2026-10-18
items:
  - Figures F1, F2, F4 reconciled against the finance workbook
  - Revenue chart redrawn from Client Figures, April–September
  - Support-backlog risk named under This month
  - Brief delivered as PDF
fields:
  - {label: Accepted by, bind: signer}
  - {label: Note, bind: note, optional: true}
decision: {label: Sign off, action: sign-off}
```

## Review notes

<!-- night: notes -->
<!-- /night: notes -->
