---
title: Agent Desk
category: learn-flow
summary: "Hand work to Claude Code or Codex, review every change they make, and keep a record of who wrote what."
tags: ["agent-desk", "example"]
jobs:
  - kind: gather
    definition: Desk Refresh.md
    as: review
  - kind: keep-sources-fresh
    watch: ["Agent Tasks.md", "Agent Brief.md"]
---
# Agent Desk

**Your agents write; you decide.** An agent working in this folder, from a terminal or from Flow, changes files the way a colleague would. Each change arrives in **Review Changes** as *Changed by Claude Code* or *Changed by Codex*.

## Waiting for your review

<!-- data: data/review-*.json#waiting -->
| Id | Task | Agent | Status |
| --- | --- | --- | --- |
| T2 | Tighten the pricing page copy | Codex | Waiting |
| T4 | Update the changelog from merged work | Codex | Waiting |

## How the record is kept

**History** records the writer of every version, and each run's receipt shows whether it was *Included* in the plan you already pay for. Nothing an agent writes becomes final until you keep it.

## Review notes

<!-- night: notes -->
<!-- /night: notes -->
