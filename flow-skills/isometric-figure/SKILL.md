---
name: isometric-figure
title: Isometric Figure
line: A layered stack in depth; press a layer to read what it does
description: Draw the layers, tiers or levels the text describes as an isometric stack, bottom layer first, and let the reader press each layer to lift it and read what the text says it does. Use when a document describes something built in layers — a technology stack, an organisation's tiers, a product's levels.
license: MIT
kind: figure
output: [figure]
version: 1.0.0
---
# Isometric Figure

An isometric figure draws layers as slabs seen from above and to one side,
so the reader sees at once what rests on what. Pressing a slab lifts it
and shows what the text says that layer does.

## Steps

1. **List the layers** the text describes, from the foundation up, with
   each one's name and one line on what it does in the text's words. Three
   to six layers; if the text gives more, keep the ones it says most about.
2. **Draw each layer as an isometric slab**: a top face as a rhombus, two
   side faces below it, each slab the same width and stacked with a small
   gap. The top of a slab at (x, y) on a 2:1 grid is the path
   `M x y l w h l -w h l -w -h z` with `h` half of `w`. The foundation sits
   lowest. Label each slab with its name on the front of its top face,
   below the slab above it, so no label crosses an edge.
3. **Give the root one state per layer** after a first state `all`
   (`data-flow-state="all base middle top"`), and make each slab a press
   for its own state (`data-flow-press="state=middle"`). In a layer's
   state, lift its slab (a `transform` in the style) and show a note beside
   it with the text's line for that layer; hide the other notes.
4. **Title it with what the stack is** (for example "The product rests on
   three layers") and say the stack in one sentence in the figure's
   `aria-label`.

## Rules

- One figure and nothing else.
- Every layer name and line is the text's; never add a layer the text does
  not describe.
- One hue in three shades for each slab's faces (top lightest), the pressed
  layer in the accent.
- Draw on a filled background so it reads on a light or a dark page, with
  text at 12 or larger at the figure's own width.

See `examples/stack.md` for a worked input and output.
