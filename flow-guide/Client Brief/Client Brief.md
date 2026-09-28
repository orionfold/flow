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
---
# Client Brief

**Harbour Analytics · fictional monthly brief · September 2026**

Revenue and accounts grew; the support backlog grew faster. The brief below cites the client's own files, which were imported into `client-files/`.

## What changed since last month

<!-- data: data/review-*.json#changed -->
| Id | Figure | Last month | This month | Source |
| --- | --- | --- | --- | --- |
| F1 | Monthly recurring revenue | $184,000 | $191,500 | Finance workbook |
| F2 | Active accounts | 412 | 418 | Finance workbook |
| F4 | Open support tickets | 38 | 52 | Support export |

## This month

Recurring revenue rose to $191,500 and active accounts to 418. Open support tickets rose from 38 to 52, which the August board deck names as the quarter's top operating risk. **Expand with Sources** can draft this section from the files in `client-files/`; every sentence it proposes cites one, and you keep or revert each change.

## Next month

Import the new files into `client-files/`, update [Client Figures](Client%20Figures.md), and **Run Jobs**: the table above redraws, and the brief shows what changed. **Publish** writes the PDF or Word file the client receives.

## Review notes

<!-- night: notes -->
<!-- /night: notes -->
