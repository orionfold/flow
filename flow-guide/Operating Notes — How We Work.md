---
title: Operating Notes — How We Work
tags: [operating, handbook, team]
---

# Operating Notes — How We Work

**Owner:** the team · **Date:** October 28, 2026 · **Status:** living

A short handbook for how documents move through this company. It exists
because the same four questions kept getting asked in Slack, and a
document that answers them is cheaper than answering them again.

## The four questions

![A shared table mid-review](assets/meeting-table.jpeg)

*Documents circulate with their own history attached; the review happens around them, not in a separate system.*

**Where does a document live?** In a folder, as a Markdown file, with
its images beside it in `assets/`. There is no library to import into
and no format to export from. Every other tool on the machine can read
these files while we are working on them.

**Who approved this change?** The document says so. An AI-assisted
change arrives as a proposal with the exact diff, and approving it
appends a record naming what ran and what it cost. A change nobody
approved did not happen.

**How do I find that passage from three months ago?** Search, then open
the result. It scrolls to the exact passage and highlights it — and if
the document moved on since, it finds the passage where it went rather
than highlighting whatever drifted into that position.

**What is it doing right now?** The title bar answers this. Memory,
CPU, GPU, and the machine's heat in plain words, plus the model that is
running if one is. The fan question has an answer that does not require
opening Activity Monitor.

## Conventions we actually keep

| Convention | Why | Enforced by |
|:-----------|:----|:------------|
| Front matter on every document | Owner and date survive a rename | Habit |
| Images in `assets/`, never absolute paths | The folder stays portable | The app refuses paths outside it |
| Tables written spaced, `\| a \| b \|` | Readable as plain text in a diff | Habit |
| Decisions get their own document | A decision buried in a thread is lost | Review |
| Nothing gets deleted, things get archived | The Trash is the system's, not ours | The app |

## The editing rules

- **Auto-save is on**, five seconds after you stop typing. Command-S
  still works whenever you want it. A document that cannot be saved
  keeps its dot and its text — it never silently loses either.
- **A file that changed on disk underneath you is never overwritten.**
  If two people opened the same document, the second save says so
  instead of quietly winning.
- **A change waiting on approval waits for you.** Auto-save does not
  write out a decision you have not made.

## Things we tried and stopped doing

- **Per-team folders.** Documents crossed teams constantly and the
  folder became a filing argument. One folder per project instead.
- **A weekly "document health" review.** It produced a scoreboard
  nobody acted on. The per-document record made it redundant.
- **Naming conventions with dates in the filename.** The modified date
  is already there and it does not go stale when a document is revised.
