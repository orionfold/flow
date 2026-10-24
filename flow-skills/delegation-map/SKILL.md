---
name: delegation-map
title: Delegation Map
line: Who does each step, and where the work changes hands
description: Draw who carries each step of a piece of work, one lane per person or team, with the hand-offs between them, as a diagram. Use when a document describes a process that several people or teams share.
license: MIT
kind: method
output: [mermaid]
version: 1.0.0
---
# Delegation Map

A delegation map shows ownership and hand-offs. Most delays live at the
hand-offs, so every arrow that crosses a lane is one the reader should be
able to see.

## Steps

1. **List the steps** the text describes, in order, each with the person,
   role or team that carries it. A step with no owner in the text goes in
   a lane called *Unassigned*.
2. **Group the steps into lanes**, one per owner, in the order the owners
   first appear.
3. **Draw one flowchart**: `flowchart LR`, one `subgraph` per lane titled
   with the owner, one node per step in its lane, and an arrow for each
   step that follows another. Label an arrow when the text says what is
   handed over ("signed contract").
4. **Name the hand-offs**: one line after the diagram counting the arrows
   that cross lanes and naming any that the text says are slow or unclear.

## Rules

- One diagram and one line. A short heading is allowed; nothing else.
- Step names are the text's own, in a few words; owners are as the text
  names them (a role, not a guessed person).
- Never add a step the text does not describe.

See `examples/customer-onboarding.md` for a worked input and output.
