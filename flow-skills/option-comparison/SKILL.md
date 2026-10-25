---
name: option-comparison
title: Option Comparison
line: Options side by side on the facts that tell them apart
description: Put the options a text weighs side by side on the facts it gives — cost, time, risk, what each makes possible — in one table, and chart the one measure that separates them most when they share one. Use when a document is choosing between a few ways forward.
license: MIT
kind: method
output: [table, chart?]
needs: [points 2]
version: 1.1.0
---
# Option Comparison

An option comparison lets a reader see the trade-off rather than be told
it. It keeps each option's facts in the same columns, so a gap — a cost
nobody stated, a risk only one option names — is visible as an empty
cell.

## Steps

1. **List the options** the text weighs, including "do nothing" when the
   text treats it as one. Use each option's own name from the text.
2. **Pick the dimensions** the text uses to tell them apart — cost, time,
   people, risk, reversibility, what it unlocks — in the order the text
   gives them weight. Keep a dimension only when the text gives it for at
   least two options; a fact about one option alone belongs in the
   closing sentence, not in a column of "not stated".
3. **Write the table**: one row per option, one column per dimension, each
   cell the text's fact in a few words. A fact the text does not give is
   "not stated", never an estimate.
4. **Chart only a like-for-like measure.** Chart a dimension only when it
   is one measure in one unit — a first-year cost, a time in weeks — and
   the text gives a number for at least two options. Pick the one that
   separates them most: one bar chart, one bar per option with a number,
   titled with what it shows ("Renting costs a third of building in year
   one"). Leave off an option with no number rather than drawing it as
   zero. A cost of a different kind — a monthly spend beside a share of
   revenue beside a credit per customer — is not one measure. When no
   dimension qualifies, draw no chart and say why in the closing sentence
   ("The three costs are of different kinds, so they are compared in the
   table only").
5. **Name the trade-off** in one sentence under the chart, or under the
   table when there is no chart: what the leading option gives up.

## Rules

- One table, at most one chart, one sentence. A short heading is allowed;
  nothing else.
- Never `highlight` a bar whose value is zero or missing; highlight the
  option the title names.
- No scores and no weights — that is a scorecard's job. This method keeps
  the text's own facts.
- Never recommend an option the text does not; name the trade-off.

See `examples/analytics-stack.md` for a worked input and output.
