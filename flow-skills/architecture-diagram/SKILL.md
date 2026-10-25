---
name: architecture-diagram
title: Architecture Diagram
line: The parts of a system, where they run, and what flows between
description: Draw the parts of a system a text describes, grouped by where they run or who controls them, with the data that moves between them labelled, as a diagram. Use when a document explains how a product, service or pipeline is put together.
license: MIT
kind: method
output: [mermaid]
needs: [points 2]
version: 1.1.0
---
# Architecture Diagram

An architecture diagram answers three questions at once: what the parts
are, where each one runs, and what crosses each boundary. The boundaries
are often the point — what leaves the device, what reaches a third
party — so they are drawn, not implied.

## Steps

1. **List the parts** the text names — apps, services, stores, models,
   people, outside services — in the text's words.
2. **Find the boundaries** the text draws: a device, a cloud account, a
   vendor, a network, a team. Each becomes a group; a part the text does
   not place goes outside every group.
3. **List the flows**: for each pair of parts the text connects, what
   moves between them and in which direction.
4. **Draw one flowchart**: `flowchart TB`, one `subgraph` per boundary
   titled with its name, one node per part (a cylinder `[( )]` for a store,
   a box for everything else), and one labelled arrow per flow. Top to
   bottom keeps the diagram as wide as the page however many parts there
   are; a left-to-right row runs off the page's edge past three or four.
5. **Name what crosses a boundary**: one line after the diagram listing
   each flow that leaves one group for another.

## Rules

- One diagram and one line. A short heading is allowed; nothing else.
- Never add a part, a flow or a boundary the text does not describe.
- Label every arrow with what moves, in a few words.

See `examples/note-app.md` for a worked input and output.
