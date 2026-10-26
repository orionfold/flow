---
name: scenario-model
title: Scenario Model
line: Low, base and high cases from stated ranges, and a choice
description: Turn the ranges a text gives into a low, a base and a high case, chart the outcome of each, and add a form to record which case the plan follows and why. Use when a document plans against an uncertain number.
license: MIT
kind: method
output: [flowui, chart]
needs: [numbers 2]
version: 1.0.1
---
# Scenario Model

A scenario model replaces one confident forecast with the range the text
actually supports, so a plan can be tested against its bad case as well as
its good one.

## Steps

1. **Find the uncertain driver** — demand, price, a conversion, a date —
   and the range the text gives for it: a low, a likely and a high value,
   or a figure with a stated margin.
2. **Build three cases**: *Low*, *Base* and *High*, each the driver's value
   carried through to the outcome the text cares about, by the arithmetic
   the text implies. When the text gives only one value, stop and say in
   one line that there is no range to model.
3. **Draw the outcome** as one bar chart, one bar per case, every value
   from step 2, titled with what the spread means ("Even the low case
   covers the hire").
4. **Add the choice**: one Form with a choice field whose options are the
   three case names written plainly (Low, Base, High — the figures belong
   in the arithmetic, not in the options), a text field for the reason and
   a field for who decides, and the *decide* act, so the case the plan
   follows is recorded.

## Rules

- One chart and one form, and a sentence of arithmetic per case. A short
  heading is allowed; nothing else.
- The base case is the text's likely value, never the middle of the range
  by default.
- Every case states its driver value, so a reader can redo it.

See `examples/next-quarter.md` for a worked input and output.
