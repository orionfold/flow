---
name: isometric-figure
title: Isometric Figure
line: A layered stack in depth; press a layer to read what it does
description: Draw the layers, tiers or levels the text describes as an isometric stack, bottom layer first, and let the reader press each layer to lift it and read what the text says it does. Use when a document describes something built in layers — a technology stack, an organisation's tiers, a product's levels.
license: MIT
kind: figure
output: [figure]
needs: [points 2]
version: 1.2.0
---
# Isometric Figure

An isometric figure draws layers as slabs seen from above and to one side,
so the reader sees at once what rests on what. Pressing a slab lifts it
and shows what the text says that layer does.

## Steps

1. **List the layers** the text describes, from the foundation up, with
   each one's name and one line on what it does in the text's words. Three
   to six layers; if the text gives more, keep the ones it says most about.
2. **Draw each layer as an isometric slab** on this grid, so every name
   and object stays inside its own face. A slab's top face is the rhombus
   `M 230 y l 160 80 l -160 80 l -160 -80 z`; its two sides hang 20 below
   the face's front edges. The top slab's back corner is at y = 40 and
   each slab below sits 140 lower, so the front of every face shows. On
   each face:
   - the **name**, horizontal and never rotated, centred at x = 280 with
     its baseline at y + 80; a name over 22 characters wraps to two lines
     at y + 68 and y + 84;
   - an **object** that is what the layer is (gears for a process or a
     mechanism, a page for a document, a window for an app, discs for
     data, a person for a team), standing or lying on the face around
     (150, y + 72), at most 52 wide and 56 tall.
3. **Colour each layer** with its own hue (teal, violet, blue, orange,
   red, green, bottom up): a light tint of it on the top face, the hue
   itself on the sides at a little transparency, and a white sheen
   (a gradient from 70% to clear) over the top face, so the slabs read
   as glass. Give the dark page its own rules under
   `@media (prefers-color-scheme: dark)`: light text,
   and the hue at 35% on each top face, so the slab below shows through.
4. **Give the root one state per layer** after a first state `all`
   (`data-flow-state="all base middle top"`), and make each slab a press
   for its own state (`data-flow-press="state=middle"`). In a layer's
   state, lift its slab (a `transform` in the style), outline its top face
   in the accent, and show a note at x = 430 with the text's line for that
   layer; hide the other notes.
5. **Title it with what the stack is** (for example "The product rests on
   three layers") and say the stack in one sentence in the figure's
   `aria-label`.

## Rules

- One figure and nothing else.
- Every layer name and line is the text's; never add a layer the text does
  not describe.
- No label crosses an edge or sits under the slab above it; shorten an
  object before a name.
- Every word right of the stack stays between x = 430 and 700: a line
  holds at most 36 characters at 13, and a longer one wraps onto the next
  line. The title is the `<title>`; draw no heading over the notes.
- Draw no background: the figure sits on the page, so give it no backdrop
  rect, colour it to read on a light or a dark page, and keep text at 12 or
  larger at the figure's own width: 720 wide, and 260 tall
  plus 140 for each layer after the first.

See `examples/stack.md` for a worked input and output.
