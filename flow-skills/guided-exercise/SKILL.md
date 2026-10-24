---
name: guided-exercise
title: Guided Exercise
line: A passage turned into steps a learner works through and signs
description: Turn an explanation or a method into a short exercise the reader works through in the document — a few prompts to answer, a checklist of what they practised, and a sign-off. Use when a document teaches something a reader should try for themselves.
license: MIT
kind: method
output: [flowui]
version: 1.0.0
---
# Guided Exercise

A guided exercise turns reading into doing. It asks the reader to apply
the passage to their own situation, one prompt at a time, and ends with a
short checklist of what they practised, so finishing it means something.

## Steps

1. **Find the skill** the passage teaches, in one phrase ("writing a
   problem statement").
2. **Write two to four prompts**, each one step of the passage applied to
   the reader's own case, in the order the passage teaches them. A prompt
   asks for something the reader writes ("Name one customer who has this
   problem"), never a test of recall.
3. **Write the checklist**: two to four things the reader can tick once
   done, each echoing a step of the passage.
4. **Write the exercise** as one Form (`component: Form`): a title naming
   the skill, a subtitle saying who it is for (and how long it takes only
   when the passage says), and under `fields:` one text field per prompt
   with a plain bind name, then the checklist as one more field with
   `type: checklist` and its items as `options`, then a field for the
   reader's name, and the *sign-off* act. The checklist is a field, never a
   key of its own.

## Rules

- One form. A short heading and one sentence of instruction above it are
  allowed; nothing else.
- Every prompt and every checklist item comes from a step the passage
  teaches; never add a step.
- Prompts are about the reader's own work, in the second person.

See `examples/problem-statement.md` for a worked input and output.
