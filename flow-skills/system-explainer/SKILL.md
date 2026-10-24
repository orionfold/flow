---
name: system-explainer
title: System Explainer
line: A system's parts, its flows, and what a failure changes
description: Draw a system the text describes as its parts and the flows between them, step through one request or item travelling it, and let the reader press the weak point the text names to see what changes when it fails. Use when a document describes how components, teams or stages pass work to each other.
license: MIT
kind: figure
output: [figure]
version: 1.0.0
---
# System Explainer

A system explainer shows the parts of a system and what passes between
them, then follows one thing through it. Its press answers the question a
reader asks next: *what happens when this part fails?*

## Steps

1. **List the parts** the text names (services, teams, stages, stores) and
   **the flows** between them (what goes from which part to which). Use the
   text's names. Leave out any part nothing flows to or from.
2. **Pick the one path** the text follows or implies, from where work
   enters to where it ends. Its hops become the steps (`data-flow-step` 1,
   2, 3…), each hop's arrow and a one-line label from the text.
3. **Find the weak point** the text names: a part it says can fail, slow
   down or become a bottleneck. Give the root two states, `normal` first
   and then `failed`, and make that part a press
   (`data-flow-press="state=failed"`). In the failed state, mark that part
   and every flow the text says depends on it, and show the text's own
   words for what happens instead. If the text names no weak point, give
   the figure steps only.
4. **Lay the parts out** in the direction the work moves, entry on the left
   or the top, with no crossing arrows where a reorder avoids one.
5. **Title it with what the system does** (for example "Orders reach the
   warehouse through one queue") and put the whole picture in one sentence
   in the figure's `aria-label`.

## Rules

- One figure and nothing else.
- Every part, flow and consequence is the text's; a failure the text does
  not describe is not drawn.
- Grey for the parts, one colour for the path being followed, and red only
  for the failed state.
- Draw on a filled background so it reads on a light or a dark page, with
  text at 12 or larger at the figure's own width.

See `examples/orders.md` for a worked input and output.
