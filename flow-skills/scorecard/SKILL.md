---
name: scorecard
title: Scorecard
line: Each candidate scored against weighted criteria, then signed off
description: Score candidates, vendors, people or proposals against the criteria a text sets, weight them, total them in a table, and add a sign-off for whoever confirms the scores. Use when a document compares a few candidates against stated criteria.
license: MIT
kind: method
output: [table, flowui]
needs: [points 2]
version: 1.0.0
---
# Scorecard

A scorecard makes a judgement repeatable: the same criteria, the same
scale, a weight for what matters most, and a reason beside every score so
someone else can check it.

## Steps

1. **Name the criteria** the text sets or clearly implies, and a weight for
   each that sums to 100. Use the text's weights when it gives them. When
   it only ranks the criteria, use rank-sum weights — of n criteria, the
   first gets n parts, the next n − 1, down to 1, each part 100 divided by
   the sum of the parts — and say so in one line. When it does neither,
   weight them equally and say so.
2. **Score each candidate from 1 to 5** on each criterion, from what the
   text says about it. When the text says nothing about a candidate on a
   criterion, write "—" and leave it out of that candidate's total.
3. **Total** each candidate as the weighted average of the scores it has,
   to one decimal.
4. **Write the table**: one row per criterion with its weight and each
   candidate's score, a last row with the totals, and a *Why* line under
   the table for each score that is not obvious from the text.
5. **Add the sign-off**: one Form (`component: Form`) whose fields are a
   checklist field (`type: checklist`) of what the reviewer confirms — the
   criteria, the weights, the scores — and a field for who signs, with the
   *sign-off* act. The scores live in the table, never in the form.

## Rules

- One table, its *Why* lines, and one sign-off form. A short heading is
  allowed; nothing else.
- Never score a candidate on something the text does not say.
- The candidate with the highest total is named in the heading only when
  every candidate has a score on every criterion.

See `examples/vendors.md` for a worked input and output.
