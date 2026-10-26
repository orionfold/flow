---
name: workflow-path
title: Workflow Path
line: A workflow drawn as what goes in, the work, and what comes out
description: Draw the workflow a passage narrates as one path, the way Flow's Welcome paths draw theirs. The files and sources go in, the work happens in the middle, the deliverables come out, and the acts the text names ride the arrows. It builds in five steps. Use when a document describes a recurring piece of work and a reader should see its shape at a glance.
license: MIT
kind: figure
output: [figure]
needs: [points 2]
version: 1.0.0
---
# Workflow Path

A workflow path is the whole job in one row: what goes in, the one piece
of work it becomes, and what comes out the other side. It is the picture
on a Welcome path in Flow, drawn from the reader's own workflow. It is not
a process map of every step.

## Steps

1. **Find the inputs, the work and the deliverables** the text describes.
   - Inputs: one to three files or sources that go in.
   - Work: the one thing they become.
   - Deliverables: one or two things that come out.
   If the text gives more inputs, group them the way the text does ("the
   receipts"). If it gives none, draw the work and the deliverable alone.
2. **Name each mark.** A file is a folded page with its extension inside
   (CSV, PDF, XLSX, DOCX…), using the extension the text gives or the
   plainest one its words imply. Put the text's short name for it under the
   page (*statement*, *receipts*). A source that is not a file gets an
   outline glyph:
   - a folder;
   - a terminal;
   - the web (a globe);
   - code (braces);
   - history (a clock).
3. **Draw the work as a page** in the centre: a rounded page tinted in the
   path's one hue, with "M↓" in its corner, four short text lines and two
   citation dots.
4. **Put at most two acts on the arrows**, one each side of the centre, and
   only acts the text names. Each act is a small square filled in the hue
   with a white glyph, chosen by what the act does:
   - check, approve, review or reconcile: a check mark;
   - send, post or publish: a paper plane;
   - search or find: a magnifier;
   - schedule or repeat: a clock;
   - ask or discuss: a speech bubble;
   - count, chart or measure: three bars.
   The act's own word from the text sits under the arrow. An arrow the text
   gives no act for is a plain arrow. Never add a step, a tool or a Flow
   feature the text does not name.
5. **Write three captions** under the row, five words or fewer each, in the
   text's words: what goes in (left-aligned), what the work makes (centred),
   and what comes out (right-aligned). Each caption fits under its own
   third of the row. A caption that would run into its neighbour is
   shortened, never overlapped.
6. **Build it in five steps** (`data-flow-step` 1–5):
   1. the inputs and the first caption;
   2. the first arrow;
   3. the centre and the second caption;
   4. the second arrow;
   5. the deliverables and the third caption.
7. **Title it with what the work turns into** (for example "The month's
   files become a summary and an updated ledger"), never "Workflow path".
   Say the whole path in one sentence in the figure's `aria-label`.

## Look

- **Layout**: one row, left to right. Inputs side by side, an arrow, the
  centre page about 90 wide and 110 tall, an arrow, the deliverables side
  by side. The captions sit on one line below.
- **One hue** for the whole path. Pick from teal, indigo, orange, green,
  pink, blue, purple, mint, brown, cyan, red or yellow. These are macOS
  system colours: teal is `rgb(48, 176, 199)` light and `rgb(64, 200, 224)`
  dark.
- **Hue usage**:
  - The centre page is filled with the hue at 0.13 and stroked at 1.5.
  - Its text lines are the hue at 0.45.
  - The arrows and the act squares are in the hue.
- **Files and outline glyphs** are muted: the hue mixed about halfway
  toward grey, as a thin outline with no fill. Write that mix as a literal
  colour, never `color-mix()`.
- **Arrows** are straight, with an arrowhead.

## Rules

- One figure and nothing else.
- Every name, act and caption comes from the text. A part the path needs
  but the text does not give is drawn as *Not in the text*.
- Declare each glyph once in `<defs>` as a `symbol` and place it with
  `use`.
- Write every colour as a literal value. Give the dark colours in an
  `@media (prefers-color-scheme: dark)` block.
- Any motion, such as a dash travelling along an arrow, goes inside
  `@media (prefers-reduced-motion: no-preference)`.
- Draw no background. The figure sits on the page, so give it no backdrop
  rect. Colour it to read on a light or a dark page, and keep text at 12 or
  larger at the figure's own width.

See `examples/monthly-close.md` for a worked input and output.
