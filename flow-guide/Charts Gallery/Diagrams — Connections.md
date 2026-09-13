---
title: Diagrams — Connections
tags: [charts-gallery, reference, fictional-example]
---
# Diagrams — Connections

[[Charts Gallery]] · Previous: [[Diagrams — Structures]] · Next: [[Charts Gallery]]

**Organize ideas, events and quantitative flows.**

> Every exhibit on this page uses fictional teaching data or an authored scenario. Source labels describe the example; they are not reports, measured Flow benchmarks or product guarantees.

| Form | Use it for |
| --- | --- |
| Mindmap | Turn a nested outline into a navigable conceptual structure |
| Timeline | Present dated milestones in order |
| Quadrant chart | Discuss items scored on two explicit axes |
| Sankey diagram | Follow amounts between named stages |
| Pie (Mermaid) | Show a few embedded amounts within a Mermaid document |
| XY chart (Mermaid) | Combine simple embedded bar and line series using one explained axis |
| Git graph | Explain a small branch-and-merge history |

An outline, a chronology and a numerical flow should not share a form merely because all contain connections.

## The exhibits

### Mindmap

Turn a nested outline into a navigable conceptual structure. Branches are authored associations, not an automatically maintained knowledge graph.

Source: an outline, a nested bulleted list of topics and subtopics, such as meeting notes, a brainstorm, or a document's structure.

```mermaid
mindmap
  root((Board update, Q3))
    Revenue
      New ARR $687k
      NRR 112%
      Enterprise mix up
    Product
      Dictation
      Charts and diagrams
      Local runtime
    Risks
      Expansion below plan
      Hiring pace
    Asks
      Approve Q4 hiring plan
      Intro to two design partners
```

[[Charts Gallery]]

### Timeline

Present dated milestones in order. Distinguish planned dates from observed events and do not treat this fictional history as a Flow release record.

Source: a list of dated events: a company history, a release log, an incident's sequence.

```mermaid
timeline
  title Example project, from discovery to pilot
  2026-03 : Discovery interviews begin
  2026-05 : First working review is ready
  2026-06 : Team tests the local dataset
  2026-07 : Source review and corrections
  2026-08 : Documentation and handover
         : Fictional pilot opens
```

[[Charts Gallery]]

### Quadrant chart

Discuss items scored on two explicit axes. The placement is a judgment to review; a quadrant label is not a prioritization algorithm.

Source: a list of items each rated on two axes, such as effort and impact, risk and reward or urgency and importance, the prioritisation matrix.

```mermaid
quadrantChart
  title Q4 candidates by effort and impact
  x-axis Low effort --> High effort
  y-axis Low impact --> High impact
  quadrant-1 Plan carefully
  quadrant-2 Do first
  quadrant-3 Reconsider
  quadrant-4 Quick wins
  Chart gallery editor: [0.72, 0.85]
  First-run onboarding: [0.35, 0.78]
  Shared folders: [0.88, 0.70]
  Export to PDF: [0.30, 0.55]
  Custom themes: [0.45, 0.20]
  Calendar sync: [0.65, 0.30]
  Keyboard shortcut sheet: [0.12, 0.48]
```

[[Charts Gallery]]

### Sankey diagram

Follow amounts between named stages. Check units and flow conservation; these numbers are embedded in the diagram and do not update from a source table.

Source: a table of source, target and amount: where traffic, money or people flow from one stage to the next, such as a funnel or an energy balance.

```mermaid
sankey-beta
Visitors,Signed up,3200
Visitors,Bounced,9800
Signed up,Opened a folder,2100
Signed up,Never returned,1100
Opened a folder,Ran Agency,1450
Opened a folder,Write-only,650
Ran Agency,Upgraded to Pro,380
Ran Agency,Stayed free,1070
Upgraded to Pro,Upgraded to Team,96
Upgraded to Pro,Stayed on Pro,284
```

[[Charts Gallery]]

### Pie (Mermaid)

Show a few embedded amounts within a Mermaid document. It is authored data; the chart-fence pie is the choice here when values must bind to a local source.

Source: a short list of labels and amounts: the same material as a chart pie, when you want it inside a diagram-only document or rendered on GitHub.

```mermaid
pie showData
  title Where review time goes
  "Reading the proposal" : 41
  "Checking the receipt" : 18
  "Editing before approval" : 27
  "Discarding" : 14
```

[[Charts Gallery]]

### XY chart (Mermaid)

Combine simple embedded bar and line series using one explained axis. Keep units compatible and identify each series in the surrounding prose.

Source: a date-and-value table when the document must render on GitHub as well as in Flow: a bar-plus-line over months without the chart fence. Bars show signups; the line shows activated accounts. Both use account counts, not percentages.

```mermaid
xychart-beta
  title "Monthly signups and activated accounts"
  x-axis [Jan, Feb, Mar, Apr, May, Jun, Jul]
  y-axis "Accounts" 0 --> 5000
  bar [1800, 2100, 3400, 4100, 4300, 4600, 4800]
  line [1600, 1900, 3100, 3900, 4000, 4400, 4700]
```

[[Charts Gallery]]

### Git graph

Explain a small branch-and-merge history. The commits below are fictional labels; the diagram does not inspect or operate a repository.

Source: a description of branches, merges and releases: a release process, or how a feature landed.

```mermaid
gitGraph
  commit id: "initial example"
  commit id: "add table"
  branch pilot
  checkout pilot
  commit id: "review packet" tag: "example-v1"
  checkout main
  commit id: "add chart"
  commit id: "review sources"
  merge pilot
  commit id: "revise labels"
  commit id: "approve example" tag: "example-v2"
```

[[Charts Gallery]]

## Use a form with your own records

Copy the whole **Charts Gallery** folder and add that copy to Flow first. Open [[Gallery Data]] to practise with a table you can edit. [[Charts — Living Example]] shows the refresh path. These reference exhibits keep their own embedded examples; they do not change when the practice table changes.

For a new exhibit, open a suitable example in the chart editor or select your own source rows and use Visualize. Keep the units and source explanation with the result. Visualize uses your configured Agency route; inspect its proposal before applying. Authored Mermaid diagrams need deliberate text edits; they are not automatically maintained from the table.

[[Charts Gallery]] · Previous: [[Diagrams — Structures]] · Next: [[Charts Gallery]]
