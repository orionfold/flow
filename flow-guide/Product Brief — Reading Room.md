---
title: Product Brief — Reading Room
tags: [product, brief, roadmap]
---

# Product Brief — Reading Room

**Owner:** product · **Date:** November 4, 2026 · **Status:** draft for review

A proposal for the next surface: a reading mode built for long documents
that other people wrote. This brief is deliberately unfinished in its
last section — it is the one going into Thursday's review.

## The problem

![A reading setup for long documents](assets/research-desk.jpeg)

*The reader's problem, not the writer's: a long document someone else wrote.*

Our documents got longer and better, and reading them got worse. The
editor is built for the person writing; the person reading a
forty-page operating review wants something else entirely. Today they
either read in the editor, which shows them affordances they will never
use, or they export to PDF and lose every link.

The support data agrees. "How do I share this so someone can just read
it" is the third most common question and has no good answer.

## What we know from research

| Finding | Source | Confidence |
|:--------|:-------|:-----------|
| Readers scan headings first, then read one section | 14 sessions | High |
| Nobody used the outline panel we shipped in June | Usage data | High |
| Links to other documents are followed 4× more in reading mode | Prototype | Medium |
| Readers want the record of what AI touched, inline | 9 of 14 asked | Medium |
| Print is still requested by two enterprise accounts | Sales | Low |

The fourth row is the interesting one. We assumed the approval record
was a writer's concern and a reader's clutter. It is the opposite:
readers of documents they did not write want to know which parts were
machine-assisted more than the authors do.

## Proposed shape

- **A reading view that is a mode, not an export.** Same document, same
  file, different presentation. Leaving it is one gesture.
- **Headings become navigation.** The outline nobody used as a panel
  becomes the spine of the reading view itself.
- **The record travels with the document.** A reader can see what was
  AI-assisted and what was approved, without leaving the page.
- **Two panes stay available.** The comparison case — reading one
  document against another — is why people opened two panes to begin
  with.

## Open questions for Thursday

These are genuinely open. I have arguments both ways and no decision.

1. **Does reading mode allow editing at all?** A typo you cannot fix
   while reading is infuriating. But a mode that edits is not a mode.
2. **What happens to tables?** A wide table is the single worst thing
   about reading a long document on a laptop, and the grid is an
   editing surface, not a reading one.
3. **Is this one feature or two?** Reading long documents and sharing
   documents with people who do not have the app may not be the same
   problem, and building them as one is how both get worse.
