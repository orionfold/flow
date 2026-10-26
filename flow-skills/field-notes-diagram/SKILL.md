---
name: field-notes-diagram
title: Field-Notes Diagram
line: A technical idea's numbers drawn to scale, field-notes style
description: Draw the numbers a technical passage gives as one infographic in the field-notes manner, with monospace labels, one-hue gradients, every quantity drawn to its value and printed beside it, and the one number the text stresses as the thesis. It reveals in two or three steps. Use when a passage explains a technical concept through measurements, sizes, costs, timings or counts, and a reader should see their proportions.
license: MIT
kind: figure
output: [figure]
needs: [numbers 2]
version: 1.0.0
---
# Field-Notes Diagram

A field-notes diagram is a notebook figure. A few numbers, drawn
exactly to their size, make one point the reader can see before they
read it. It is precise and quiet: one thesis in colour, the rest in a
calm accent, and nothing decorated past what the numbers say.

## Steps

1. **Find the numbers and the point.** List every quantity the text
   gives, with its unit and its name, and the one claim the text makes
   about them (*the server's answer is half the wait*). That number is
   the thesis.
2. **Pick one kind** from the shape of the numbers:
   - **to-scale bars**: parts of a whole or sizes side by side, as one
     bar per name, laid out horizontally;
   - **paired bars**: a before and an after, or two options, for each
     name;
   - **series**: one value over time, as points joined by a line;
   - **pipeline**: stages a thing passes through, as boxes left to
     right, with each stage's number under it;
   - **threshold meter**: one or more readings against a limit the
     text names, as a track with the limit marked.
   If the numbers fit none of these, draw to-scale bars.
3. **Draw every quantity to its value.** A bar's length is `value ÷
   largest value × plot width`, and a point's height uses the same
   rule. Give a value too small to see a floor of 8 units, and say so
   in a note. Print each true value beside its mark with its unit.
   Every axis starts at zero unless the text gives another baseline.
4. **Make the thesis the one coloured mark.** Draw it in the primary
   teal, with a faint row-height wash behind it and its label in bold
   teal. Draw every other mark in one accent; use more accents only
   when the text names categories, one accent per category.
5. **Reveal in two or three steps** (`data-flow-step`). Show the
   context first, then the thesis and the anchor line that states the
   point with its numbers (*SERVER ANSWER: 1.2 OF 2.4 S, HALF THE
   WAIT*).
6. **Title it with the point** (for example "The server's answer is
   half of a 2.4 s page load"). Put a short uppercase eyebrow at the
   top that names what is measured. State every number in the figure's
   `aria-label`.

## Look

- **Size and type**: draw at `viewBox="0 0 600 400"`. All text is
  monospace (`ui-monospace, Menlo, monospace`):
  - the eyebrow 15, uppercase, letter-spacing 0.18em, muted;
  - labels 16, semibold;
  - values and the anchor line 13, muted.
- **Fills**: a vertical linear gradient of the mark's own hue:
  - accent marks from 0.42 to 0.14 opacity, stroked at 1 in their hue;
  - the thesis from 0.55 to 0.18, stroked at 2.
  Never use a solid fill or a filter.
- **Colours**: the light values first, then the dark ones in an
  `@media (prefers-color-scheme: dark)` block. Put a gradient's colour
  on its `stop` elements through classes, so the dark block can change
  it.
  | Role | Light | Dark |
  | --- | --- | --- |
  | Ink | `#1d2230` | `#e9ecf0` |
  | Muted | `#5b6170` | `#8b929c` |
  | Primary (thesis) | `#0e9e98` | `#14c8c0` |
  | Accent blue | `#2b5fc4` | `#7aa2f7` |
  | Accent green | `#2f8a3e` | `#5fc77a` |
  | Accent orange | `#b8641a` | `#f0a35a` |
  | Accent purple | `#7a4fc7` | `#b693f0` |
  | Accent red | `#c23a32` | `#f07a72` |
- **Points**: a halo (radius 16 at 0.22) under a core (radius 6).
- **Connectors**: 2 wide with round caps. A boundary or a limit is
  dashed `4 6`.
- **Motion**: bars grow from the left, and labels and values rise 12
  units and fade in, staggered by 0.1 s in reading order. Key every
  animation on `g:not(.flow-figure-ahead)` so each step animates as it
  appears, and put all of it inside `@media (prefers-reduced-motion:
  no-preference)`.

## Rules

- One figure and nothing else.
- Every number, name and unit comes from the text. Never round a
  number the text states, and never compute a new one other than the
  scale. A number the point needs but the text does not give is drawn
  as *Not in the text*.
- Exactly one thesis.
- Write every colour as a literal value. A CSS variable draws nothing
  here.
- Draw no background. The figure sits on the page, so give it no
  backdrop rect; a row-height wash behind the thesis is the only tint
  allowed. Keep text at 12 or larger at the figure's own width.

See `examples/page-load.md` for a worked input and output.
