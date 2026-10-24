---
name: value-model
title: Value Model
line: The value a change creates, from its stated assumptions
description: Build a small value model from the assumptions a text states — volume, rate, unit value — show the result as a chart, and give the person a form to change each assumption. Use when a document argues that something is worth doing and gives numbers for it.
license: MIT
kind: method
output: [flowui, chart]
version: 1.0.0
---
# Value Model

A value model turns a claim ("this will save us a lot") into a product of
assumptions a reader can see and change: how many, how often, how much
each. The result is only as good as its assumptions, so the model shows
them first.

## Steps

1. **Find the outcome** the text claims — a saving, revenue, hours, risk
   removed — and the period it is measured over.
2. **List the drivers** the text gives for it, each with its number and
   unit: a volume (tickets a month, users, orders), a rate (the share
   affected, a conversion, a churn), a unit value (cost per ticket, price,
   minutes). Use only numbers the text states. When the text is missing a
   driver the outcome needs, stop and say which one in one line instead of
   modelling.
3. **Compute the outcome** as the product of the drivers, over the text's
   period, and say the arithmetic in one sentence ("1,200 tickets a month ×
   a third × $18 = $7,200 a month").
4. **Write the assumptions form**: one Form whose fields are the drivers,
   each a number field with a plain bind name and the bounds the text
   implies (a share between 0 and 100), and one *update* act, so a person
   can revise the assumptions and keep them in the document.
5. **Draw the result** as one bar chart: the outcome's parts or the
   before-and-after, every value from step 3. Title it with the result
   ("Self-serve intake saves about $86,400 a year"), not "Value model".

## Rules

- One sentence of arithmetic, one form and one chart. A short heading is
  allowed; nothing else.
- Never round a stated number before computing; round only the result.
- A driver the text does not give is a gap to name, never a number to
  supply.

See `examples/assumptions.md` for a worked input and output.
