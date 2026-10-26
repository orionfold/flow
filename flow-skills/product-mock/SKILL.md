---
name: product-mock
title: Product Mock
line: A user journey played out in a mock of the product's window
description: Draw the user journey a passage describes as a mock of the product's window, whose surfaces change one step at a time, in the manner of an animated product demo. A reader steps through what the person does and what the product shows back. Use when a document describes how someone uses a product, a feature or a prototype, and a reader should see it happen.
license: MIT
kind: figure
output: [figure]
needs: [points 3]
version: 1.0.0
---
# Product Mock

A product mock is a still demo. It shows one window of the product and
plays the journey inside it: the person picks something, the product
shows it, they press something, the product answers. It shows only the
surfaces the journey touches, and only what the text says is on them.

## Steps

1. **Find the journey's beats**: three to five moments, each either
   something the person does (opens, picks, types, presses) or something
   the product shows back (a page, a list, a status, a record). Keep the
   text's order.
2. **Find the surfaces** the beats touch, from the text only:
   - a list or sidebar;
   - a main page;
   - a side panel;
   - a button or a field.
   Draw no surface the journey does not touch.
3. **Draw one window**: a rounded rectangle a few units inside the
   figure's edge, a title bar with three traffic-light dots and the
   product's name, then the surfaces as columns. The window is the
   product's own surface, not a page backdrop. It must start away from
   the figure's corner, never at 0, 0.
4. **Write only what the text gives.** A name, an amount, a status or a
   button label the text states is drawn as text. Everything else on a
   surface is a grey placeholder bar, never invented words or numbers.
   The product's name is the text's; if the text names none, the title
   bar is left blank.
5. **Make each beat a step** (`data-flow-step`), shown cumulatively:
   - a selection highlights a row;
   - a page fills in;
   - a focus ring marks what the next act is on;
   - a button appears, then is drawn pressed with a pointer at its
     corner;
   - a status pill or a timeline entry appears.
6. **Title it with what the journey achieves** (for example "One press
   sends a reminder and records it"). Say the whole journey in one
   sentence in the figure's `aria-label`.

## Look

- **Size**: `viewBox="0 0 640 400"`, with the window at
  `x="8" y="8" width="624" height="384" rx="12"`.
- **Chrome**: a pale title bar with a hairline under it and traffic
  lights `#ff5f57`, `#febc2e`, `#28c840`. A sidebar about 160 wide, a
  main column, and a side panel about 175 wide only if the journey
  touches one. Separate them with hairlines.
- **Type**: `system-ui`. The page title is 20 bold, items and labels 13,
  small print and placeholder headings 12. Headings are uppercase and
  muted.
- **One tint** for selection, focus and the main button (a blue such as
  `#2f6fd6`). Success is green: a pill `#dff3e7` with text `#146a3f`.
- **Dark**: give every colour its dark value in an
  `@media (prefers-color-scheme: dark)` block: the window `#232528`,
  panels `#2b2e32`, hairlines `#3a3f45`, ink `#eef1ef`, muted `#98a29e`.
- **Motion**: what a step adds rises 6 units and fades in. A pressed
  button dips to 0.94 scale and back. Key every animation on
  `g:not(.flow-figure-ahead)` so each step animates as it appears, and
  put all of it inside `@media (prefers-reduced-motion: no-preference)`.

## Rules

- One figure and nothing else.
- Every word and number on screen comes from the text; the rest is
  placeholder bars. A beat the journey needs but the text does not give
  is labelled *Not in the text*.
- Never draw Flow's own window, toolbar or logo unless the journey is
  about Flow.
- Keep every line of text inside its surface at its size. Break a long
  line by hand, or shorten it; never let it run past the window.
- Write every colour as a literal value. A CSS variable draws nothing
  here.
- Draw no background behind the window, and keep text at 12 or larger at
  the figure's own width.

See `examples/reminder.md` for a worked input and output.
