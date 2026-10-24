---
name: landscape-map
title: Landscape Map
line: Who is in a market or field, grouped, with each one's source
description: Map the players, products or approaches a text surveys into groups, as a diagram, with a table that gives each one’s defining fact and where the text says it came from. Use when a document surveys a market, a field or a set of alternatives.
license: MIT
kind: method
output: [mermaid, table]
version: 1.0.0
---
# Landscape Map

A landscape map shows the shape of a field: which groups exist, who sits
in each, and how sure the text is about each placement. The table carries
the evidence, so the diagram can stay simple.

## Steps

1. **List the players** the text names — companies, products, projects,
   approaches — in the text's words.
2. **Group them** by the dimension the text uses to tell them apart
   (segment, approach, buyer, stage). Use the text's own group names; a
   player it does not place goes in *Unplaced*.
3. **Draw one mind map**: `mindmap`, the field as the root, one branch per
   group, one leaf per player.
4. **Write the table** under it: Player, Group, the one fact that defines
   it in the text, and *Source* — the source the text cites for that fact,
   or "the text" when it cites none.

## Rules

- One diagram and one table. A short heading is allowed; nothing else.
- Never place a player in a group the text does not support.
- Never cite a source the text does not name.

See `examples/meeting-assistants.md` for a worked input and output.
