---
name: roadmap
title: Roadmap
line: Work laid out over time, by workstream, with its milestones
description: Lay the work a text plans on a timeline, grouped by workstream, with the order it states and the milestones it names, as a Gantt diagram. Use when a document plans work with dates, durations or a sequence.
license: MIT
kind: method
output: [mermaid]
needs: [points 2, dates]
version: 1.0.0
---
# Roadmap

A roadmap shows what happens when, who carries it, and what has to finish
before something else can start. Its value is the order and the overlaps,
so every bar keeps the dates or durations the text gives.

## Steps

1. **List the pieces of work** the text plans, each with its start and its
   end or duration, and the workstream, team or phase it belongs to.
2. **Keep the dependencies** the text states ("after the migration",
   "once design is frozen") as *after* links rather than as guessed dates.
3. **Mark the milestones** — a launch, a review, a decision date — as zero-
   length milestones.
4. **Draw one Gantt diagram**: `gantt`, a title stating what the plan
   shows ("Billing ships before the pricing change"), `dateFormat
   YYYY-MM-DD`, one `section` per workstream in the text's order, and one
   task per piece of work, written `Name :id, 2026-11-03, 42d` — a short id
   of its own for every task, a start as a date or `after <id>`, then a
   length in days or an end date. A milestone is
   `Name :milestone, id, 2027-01-12, 0d`.
5. **Name what has no date.** Work the text plans that lacks a start (a
   date or a dependency) or a length (an end or a duration) is listed in
   one line after the diagram, never placed by guess.

## Rules

- One diagram and at most one line after it. A short heading is allowed;
  nothing else.
- Task names are the text's own words, short enough to read on a bar.
- A date that the text gives as a month only starts on its first day.

See `examples/billing-launch.md` for a worked input and output.
