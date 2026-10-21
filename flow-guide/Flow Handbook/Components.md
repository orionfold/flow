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

## Section and Columns

`Section` groups components under a title. `Columns` draws them two across at most; a third sits below at the whole width, and everything stacks when the column is narrow.

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
  - component: Columns
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
