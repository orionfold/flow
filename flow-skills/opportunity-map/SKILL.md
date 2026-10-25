---
name: opportunity-map
title: Opportunity Map
line: Initiatives placed by value and effort, with the case for each
description: Lay a list of initiatives, ideas or bets on a value-and-effort map, name the quadrant each falls in, and give the case for each in a table. Use when a document lists options to prioritise.
license: MIT
kind: method
output: [chart, table]
needs: [points 2]
version: 1.1.0
---
# Opportunity Map

An opportunity map puts every initiative on two axes — the value it would
create and the effort it would take — so the quick wins, the big bets, the
fill-ins and the ones to drop are visible at a glance.

## Steps

1. **List the initiatives** the text names. Use each one's own name from the
   text. Ignore anything the text does not present as an option.
2. **Score value from 1 to 10** from what the text says about outcome,
   reach, revenue, risk removed or a goal it serves. Score **effort from 1
   to 10** from what it says about time, cost, people, dependencies or
   difficulty. When the text gives no evidence for one of the two scores,
   leave that initiative off the map and say so in one line after the
   table.
3. **Name each one's quadrant**, splitting both axes at 5.5:
   - *Quick win* — value above, effort below;
   - *Big bet* — value above, effort above;
   - *Fill-in* — value below, effort below;
   - *Reconsider* — value below, effort above.
4. **Draw the map** as one scatter chart: effort on x, value on y, one point
   per initiative, its name the first column and its quadrant a column
   coloured by `color: {field: quadrant}`. Declare both scores in
   `semantic_types` as `{semanticType: Score, intrinsicDomain: [1, 10]}`, so
   the map spans the whole scale with its quadrant lines at 5.5 and each
   point carries its name. Title it with what the map shows
   (for example "Two quick wins lead the list"), not "Opportunity map".
5. **Write the table** under the chart, one row per initiative, sorted by
   quadrant (quick wins first) and then by value: Initiative, Value,
   Effort, Quadrant, and *Why* — one short sentence quoting or paraphrasing
   the text's evidence for both scores.

## Rules

- One chart and one table. A short heading above them, and the one line
  naming what was left off, are allowed; nothing else.
- Every score has its reason in the *Why* column. A score without a reason
  is a guess, and the map must not carry guesses.
- Keep every initiative's name exactly as the text writes it, so the reader
  can find it.

See `examples/initiatives.md` for a worked input and output.
