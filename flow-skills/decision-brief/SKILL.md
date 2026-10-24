---
name: decision-brief
title: Decision Brief
line: The decision, the options, a recommendation and its sources
description: Turn a discussion into a one-page decision brief — the decision to make, the context, the options in a table, the recommendation and its risks, and the sources — so someone who was not in the room can decide. Use when a document is working towards a decision.
license: MIT
kind: method
output: [table]
version: 1.0.0
---
# Decision Brief

A decision brief is written for the person who decides and was not there.
It puts the question first, the options next, and the recommendation only
after both, so the reader can disagree with it on the evidence.

## Steps

1. **State the decision** as one question with a date or a trigger, in the
   text's terms ("Do we renew Deskly before 1 December?").
2. **Give the context** in two or three sentences: why it is being decided
   now, and the constraint that matters most.
3. **Write the options table**: Option, What it means, For, Against — one
   row per option the text weighs, each cell the text's own point.
4. **Recommend** in one paragraph: the option the text favours and the
   reason it gives. When the text does not favour one, write "No
   recommendation yet" and the question it turns on, in the text's terms.
5. **List the risks** of the recommendation, one line each, and **the
   sources**: every document, person or figure the text relies on, as the
   text names them.

## Rules

- Headings in this order: Decision, Context, Options, Recommendation,
  Risks, Sources. One table; nothing else.
- Never add an option, a fact or a source the text does not give.
- Keep it to one screen; cut context before cutting options.

See `examples/desk-renewal.md` for a worked input and output.
