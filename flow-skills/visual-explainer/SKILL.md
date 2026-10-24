---
name: visual-explainer
title: Visual Explainer
line: One idea from the text, drawn so it builds step by step
description: Draw the one mechanism, process or cause and effect a passage explains as a figure that builds in steps, each step labelled in the text's own words. Use when a passage explains how something works and a reader would follow it faster as a picture.
license: MIT
kind: figure
output: [figure]
version: 1.0.0
---
# Visual Explainer

A visual explainer turns one explanation into a picture that builds in
front of the reader: the first step alone, then each next step added to
it, so the reader holds the whole idea by the last one. It is the
whiteboard sketch drawn while talking, not a diagram of everything.

## Steps

1. **Find the one idea** the text explains: how something works, what
   causes what, or the order things happen in. If it explains several,
   take the one it spends most words on.
2. **Break it into three to five steps** in the text's own order. Each step
   is one thing that happens or one part that joins, named with the text's
   words. A step the idea needs but the text does not give is drawn with
   the label *Not in the text*, never invented.
3. **Lay it out left to right or top to bottom**, one region per step, so
   each new step lands beside the last rather than on top of it. Use one
   shape per thing and an arrow per "leads to".
4. **Make each step a group** that appears in order (`data-flow-step` 1, 2,
   3…), each with a short label of five words or fewer and, under it, one
   line from the text.
5. **Title it with what the reader will understand** (for example "Cache
   misses go to the database once"), never "Visual explainer", and say
   the whole idea in one sentence in the figure's `aria-label`.

## Rules

- One figure and nothing else.
- Every label and line comes from the text. No number, name or step the
  text does not give.
- At most five steps and two colours plus grey, one of them for the step
  the text stresses.
- Draw on a filled background so it reads on a light or a dark page, with
  text at 12 or larger at the figure's own width.

See `examples/cache.md` for a worked input and output.
