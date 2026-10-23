---
title: Components
tags: ["flow", "reference", "components"]
---
# Components

A ` ```flowui ` block is a small description Flow draws as one of its own surfaces: a checklist you can sign, a chart beside the table it came from, a note that warns before you act. The description is a few plain lines — `component: <name>` first, then that component's inputs — and the block stays readable as text in any other editor.

**Use the plain fence unless you are composing.** A table is a Markdown table, a chart is a ` ```chart ` block, a diagram a ` ```mermaid ` block, a picture an image line. Reach for a component when you want parts side by side or grouped under one title, or a checklist a reader signs.

## Approval Card

A checklist a reader ticks and signs; the signature is a record beside the document, never a change to it.

```flowui
component: Approval Card
title: Delivery acceptance
items:
  - Figures reconciled
  - Brief delivered as PDF
decision: {label: Sign off, action: sign-off}
```

## Form

Fields a reader fills in the document and one act Flow records after asking. A field is `text` on one line, a `number` between a min and a max, a `date`, a `choice` of one option, a `multi-choice` of any of them, or a `checklist` ticked item by item. The act is the button: `submit` records every entry beside the document; `decide` records the chosen option and the reason; `rate` records the score out of its scale; `sign-off` signs a checklist the way an Approval Card does; `update` writes each entry into the document's front matter under the key its field binds, so a status form shows the status it last wrote. An act is once per block; the update act is the one that writes, and it asks in Review Changes.

```flowui
component: Form
title: Interview scorecard · Senior analyst
subtitle: Harbour Analytics · panel of 2026-10-23
fields:
  - {label: Score, bind: score, type: number, min: 1, max: 5}
  - {label: What stood out, bind: note}
  - {label: Interviewer, bind: signer}
decision: {label: Rate, action: rate}
```

A Form with the update act can also set up a Job; **Elements ▸ Job Form** inserts the one below, with this document's sections and the files beside it as the choices. Its `writes:` lines are the Job as **Edit Jobs** writes it, and a value in quotes such as `"{section}"` is filled from the field with that bind. Before you press the button, the line under it says what the Job will do, where its result lands and what it may spend; a Job that writes nothing into the document says so there. The new Job waits in Review Changes until you keep it. A field the Job uses fills the Job; any other field, like the budget below, is written as its own key.

```flowui
component: Form
title: Keep a section current
fields:
  - {label: Section to keep current, bind: section}
  - {label: Sources, bind: sources, type: multi-choice, options: [notes, clippings]}
  - {label: Monthly budget in dollars, bind: budget, type: number, min: 0, max: 20}
  - {label: Last day, bind: until, type: date}
decision: {label: Set up the Job, action: update}
writes:
  jobs:
    - kind: expand-with-sources
      section: "{section}"
      sources: "{sources}"
      until: "{until}"
```

A Job like this keeps its section current. Each run redrafts the section from what the sources say now, keeping what still holds, replacing what changed and dropping what no longer holds. It never appends, and it holds the section at about its own length, or at the Job's `length:` when you set one. On a night when none of its files has changed since its last draft, kept or not, it skips without calling a model and says *No change in its sources since the last draft*. A run you start yourself from **Run Jobs** always redrafts.

Ask Chat for a decision memo or a status form and it drafts one in its reply; **Agency ▸ Form** drafts one from the selected text. The Approval Card above is a Form with a checklist and the sign-off act.

## Table

Rows as maps; the first row's keys are the columns. Plain twin: a Markdown table.

```flowui
component: Table
title: This month
rows:
  - {Figure: Active accounts, Value: 418}
  - {Figure: Churn, Value: 1.1%}
```

## Chart

The chart block's lines under `chart:`. Plain twin: a ` ```chart ` block.

```flowui
component: Chart
chart:
  chartType: Bar Chart
  title: Accounts by quarter
  data:
    - {label: Q2, value: 402}
    - {label: Q3, value: 418}
  semantic_types: {label: Category, value: Amount}
  encodings:
    x: {field: label}
    y: {field: value}
```

## Diagram

Mermaid text under `diagram: |`. Plain twin: a ` ```mermaid ` block.

```flowui
component: Diagram
title: How the brief is made
diagram: |
  flowchart LR
    A[Client figures] --> B[Brief] --> C[Sign-off]
```

## Image

A picture inside the folder, with the sentence a screen reader says. Plain twin: an image line. The `alt:` is required; **Agency ▸ Describe Picture** writes one.

```flowui
component: Image
src: assets/quiet-desk.jpeg
alt: A tidy desk by a window, laptop closed
caption: Where the brief was written
```

## Diff

A change drawn the way Review Changes draws exact changes. Plain twin: a ` ```diff ` block.

```flowui
component: Diff
title: What the refresh changed
diff: |
  @@ -12,2 +12,2 @@
  -Active accounts: 402
  +Active accounts: 418
```

## Folder

A folder's files as a table. Plain twin: a ` ```flow-folder ` block, which a Jobs run keeps current; inside a component the rows are what you wrote, and no run refreshes them.

```flowui
component: Folder
folder: assets
rows:
  - {File: quiet-desk.jpeg, Size: 178715, Modified: 2026-09-12}
```

## Callout

A note or a warning in the Reader's own style — a bar, a mark and the word, so the kind is never colour alone.

```flowui
component: Callout
kind: warning
title: Figures are provisional
text: |
  September closes on the 5th; the churn figure moves until then.
```

## Change Summary

What changed in this document lately, in History's own words — newest first, who and which day beside each line, and **Show in History** to read the rest. It holds nothing of its own: the rows are History's, so they are current every time the document opens. `since` is the first day it reaches back to (the last 30 days when absent) and `limit` how many rows show before the line that counts the rest.

```flowui
component: Change Summary
title: What changed this month
since: 2026-10-01
limit: 5
```

## Sources

What this document was made from, as History records it — each source with how it was used and when, a source that changed since marked as History marks it, and a source in your folder opening on a click. A document from before Flow recorded where things came from says *Lineage not recorded.*

```flowui
component: Sources
```

Put either one under a brief that a Jobs run rewrites, and a reader sees what moved and what it rests on before trusting it.

## Section, Hero and Bento

`Section` groups components under a title. `Hero` holds exactly two, side by side at every width — the pair a page opens with, a chart beside the figures it rests on, stays a pair in a Chat reply and in a narrow window alike. `Bento` holds two or more: two across at most, a third below at the whole width, and everything stacks when the column is narrow. A block written `Columns` in an earlier Flow is read as a Bento and keeps drawing; Flow writes `Bento` from now on.

```flowui
component: Hero
components:
  - component: Chart
    chart:
      chartType: Line Chart
      title: Weekly mentions rose through September
      data:
        - {week: "2026-09-07", mentions: 120}
        - {week: "2026-09-14", mentions: 134}
        - {week: "2026-09-21", mentions: 151}
      semantic_types: {week: Category, mentions: Amount}
      encodings:
        x: {field: week}
        y: {field: mentions}
  - component: Table
    title: Figures
    rows:
      - {Figure: Assistants tracked, Value: 14}
      - {Figure: New this week, Value: 2}
```

## One composed example

```flowui
component: Section
title: Before you sign
components:
  - component: Callout
    kind: warning
    title: Figures are provisional
    text: |
      September closes on the 5th; the churn figure moves until then.

      Sign only after the close.
  - component: Bento
    components:
      - component: Image
        src: assets/quiet-desk.jpeg
        alt: A tidy desk by a window, laptop closed
        caption: Where the brief was written
      - component: Table
        title: This month
        rows:
          - {Figure: Active accounts, Value: 418}
          - {Figure: Churn, Value: 1.1%}
```

Ask Chat for a composition and it draws the block in its reply before you keep it. The card's **⊟** opens the component editor, where each part has its own controls and the block rewrites without touching the text you wrote.

## When a bound table refreshes under a signature

A `Table` or `Chart` inside a component can carry a `data:` binding, and a Jobs run refreshes its rows the way it refreshes a plain block. The refresh changes the block's bytes, so a signature on that block reads **Receipts stale** until someone signs the new figures — on purpose: a signature binds exactly what was signed.
