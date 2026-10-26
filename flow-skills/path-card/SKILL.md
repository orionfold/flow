---
name: path-card
title: Path Card
line: A feature on one card: who it is for, the steps, the path, proof
description: Draw a feature and the workflow it enables as one card, in the manner of a product's path cards. The card shows who it is for, a title, three steps, the workflow as a path, a small mock of the product at the moment that matters, and a stat line when the text gives a number. Use when a document introduces a feature, a service or an offer, and a reader should grasp it at a glance.
license: MIT
kind: figure
output: [figure]
needs: [points 2]
version: 1.0.0
---
# Path Card

A path card sells one piece of work honestly. In one card it says who it
is for, what they do in three steps, the shape of the work as a path, the
product at the moment that matters, and the proof, but only when the text
gives some. The whole card is one figure: a card's text is short enough to
wrap by hand.

## Steps

1. **Read the feature and its workflow** from the text:
   - who it is for;
   - three steps in the text's order;
   - what goes in, the work, and what comes out;
   - the moment in the product where the work happens;
   - any number the text gives as an outcome, with what it was measured
     on.
2. **Draw the card**: a rounded rectangle inset from the figure's edge, at
   `x="8" y="8"`, with a hairline border. It is the card's own surface,
   not a page backdrop.
3. **Write the top**:
   - a persona line in small uppercase, *FOR …*, in the text's words;
   - a title of eight words or fewer that says what the feature does;
   - the three steps, each numbered in the tint, each one line of nine
     words or fewer. Shorten a step rather than wrap it.
4. **Draw the path** under the steps, the way Workflow Path draws one:
   - files as muted folded pages with their extension;
   - the work as a tinted page;
   - at most two acts the text names, riding the arrows as squares
     filled in the tint;
   - three short captions under the row.
5. **Draw a small mock** under the path, the way Product Mock draws one:
   - a small window with the product's name, if the text gives one;
   - grey placeholder rows;
   - only the statuses and labels the text names;
   - the one control the work turns on.
   If the text gives no label for that control, draw it with a glyph and
   no words.
6. **Write the stat line** at the bottom, behind a hairline, only when the
   text gives a number: the number large in the stat colour, then what it
   measures and what it was measured on, in the text's words. With no
   number in the text, draw no stat line and end the card after the mock.
7. **Build it in steps** (`data-flow-step`):
   1. the path's inputs;
   2. the work;
   3. the deliverables;
   4. the press in the mock;
   5. the stat, if there is one.
   The persona, title, steps and the mock's window stay on the card from
   the start.
8. **Title the figure** with the card's title. Say the whole card, the
   stat included, in one sentence in the figure's `aria-label`.

## Look

- **Size**: `viewBox="0 0 640 600"`, or 640 by 520 with no stat line.
- **Type**: `system-ui`. The persona is 12 bold, uppercase, with
  letter-spacing 0.08em. The title is 22 bold, steps 15, captions 14
  semibold, small labels 12, the stat 24 bold, and its label 13.
- **Tint**: one hue for the step numbers, the path and the main control,
  for example teal `#0e9e98` (dark `#14c8c0`). The stat is a deep red,
  `#ba2d21` (dark `#f07a72`).
- **Card and window**: `#ffffff` with a `#d5dbd6` hairline. In the dark
  block, `#232528` with `#3a3f45`.
- **Motion**: what a step adds rises 6 units and fades in, and a pressed
  control dips. Key every animation on `g:not(.flow-figure-ahead)` so each
  step animates as it appears, and put all of it inside
  `@media (prefers-reduced-motion: no-preference)`.

## Rules

- One figure and nothing else.
- Every word and number comes from the text. Never invent a stat, a
  persona, a product name or a control's label. A number on the card is
  one the text states.
- Keep every line inside the card at its size.
- Write every colour as a literal value, and give the dark ones in an
  `@media (prefers-color-scheme: dark)` block.
- Draw no background behind the card, and keep text at 12 or larger at
  the figure's own width.

See `examples/reminders.md` for a worked input and output.
