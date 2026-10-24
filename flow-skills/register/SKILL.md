---
name: register
title: Register
line: Risks, issues or decisions logged with an owner and a check
description: Turn the risks, issues, assumptions or decisions a text mentions into a register — one row each, with its owner, its rating or status, and the next check — so nothing is left to memory. Use when a document raises things someone must keep an eye on.
license: MIT
kind: method
output: [table]
version: 1.0.0
---
# Register

A register is a promise to look again. Each row names what could go wrong
or what was decided, who owns it, and when it will be checked, so the list
stays live rather than being written once.

## Steps

1. **Decide the register's kind** from the text: risks, issues (things
   already wrong), assumptions or decisions. One register holds one kind;
   when the text mixes them, use the kind it has most of and say in one line
   what was left out.
2. **List the items**, each in one sentence in the text's words, numbered
   R1, R2… (or I, A, D for the other kinds).
3. **For risks, rate likelihood and impact** as Low, Medium or High from
   what the text says; for issues, decisions and assumptions, give the
   status the text gives. A rating the text gives no grounds for is
   "not stated".
4. **Name the owner** the text gives, or "Unassigned", and **the check**:
   what will be looked at, and the date or event the text ties it to.
5. **Write the table**, highest-rated risks first: ID, Item, Likelihood,
   Impact (or Status), Owner, Check.

## Rules

- One table. A short heading is allowed, and one line for what was left
  out; nothing else.
- Never assign an owner the text does not name.
- A check without a date or an event is "next review", never a guessed
  date.

See `examples/migration-risks.md` for a worked input and output.
