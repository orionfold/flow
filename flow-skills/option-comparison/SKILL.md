---
name: option-comparison
title: Option Comparison
line: Options side by side on the facts that tell them apart
description: Put the options a text weighs side by side on the facts it gives — cost, time, risk, what each makes possible — in one table, and chart the one measure that separates them most. Use when a document is choosing between a few ways forward.
license: MIT
kind: method
output: [table, chart]
version: 1.0.0
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
   gives them weight.
3. **Write the table**: one row per option, one column per dimension, each
   cell the text's fact in a few words. A fact the text does not give is
   "not stated", never an estimate.
4. **Chart the dimension that separates the options most** among those
   with a number for every option: one bar chart, one bar per option,
   titled with what it shows ("Renting costs a third of building in year
   one"). When no dimension has a number for every option, chart the one
   with the most, leave off the options it has no number for, and name
   them in one line under the chart — never an estimate in their place.
5. **Name the trade-off** in one sentence under the chart: what the leading
   option on the charted measure gives up.

## Rules

- One table, one chart, one sentence. A short heading is allowed;
  nothing else.
- No scores and no weights — that is a scorecard's job. This method keeps
  the text's own facts.
- Never recommend an option the text does not; name the trade-off.

See `examples/analytics-stack.md` for a worked input and output.
