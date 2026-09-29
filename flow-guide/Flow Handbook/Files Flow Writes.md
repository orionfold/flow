---
title: Files Flow Writes
tags: ["flow", "reference", "files"]
---
# Files Flow Writes

## Your folder stays readable without Flow

Your documents are Markdown files in folders you choose. As you work, Flow adds a few plain-text files beside a document, a few keys to its front matter, and saved versions in the folder's history. This page names each one, says whether to edit it, and shows how to read it with tools every Mac already has: `jq` and `git` in Terminal.

The commands below use a document called `Plan.md`. Run them in Terminal from the folder that holds it, with its name in place of `Plan.md`.

## Files beside a document

Each file is the document's name plus a suffix, so `Plan.md` can have `Plan.md.flow-receipts` beside it. When you rename a document in Flow, these files are renamed with it; when you move it to the Trash, they go too. Finder lists them beside the document; Flow's sidebar does not.

| File | What it holds | Edit it? | If you delete it |
| --- | --- | --- | --- |
| `Plan.md.flow-receipts` | The record of every change, check and model run on the document, one entry per line | Never; each entry is linked to the one before, so an edit breaks the record | The document keeps its text; its record of who changed what, and when, is gone |
| `Plan.md.flow-night` | The changes the Night Shift wrote, each with its before and after, and whether you kept or reverted it | Never | The changes stay in the document; Review Changes can no longer offer Keep or Revert for them |
| `Plan.md.flow-night-unreadable` | An earlier night record this version of Flow could not read, kept exactly as it was instead of written over | Never | Nothing Flow uses; the changes it recorded are still in the document and its saved versions |
| `Plan.md.flow-review` | Proposed changes waiting in Review Changes, and changes another app made that you have not reviewed | Never | The proposals waiting for you are gone; the document is unchanged |
| `Plan.md.flow-draft` | A proposal a Job prepared overnight that waits for your approval | Never | The waiting proposal is gone; the document is unchanged |
| `Plan.md.flow-publish` | How the document last went out: its formats, and for a site its repository, address, theme and navigation | Never; File ▸ Publish rewrites it each time the document goes out | Publish starts again at PDF; the document is unchanged |

### The record of changes

One line per entry, each a JSON object: when it happened, what kind of entry it is, and who made it (you, Flow, the Night Shift, or another app).

```sh
jq -c '{recordedAt, kind, by: .attester.kind}' 'Plan.md.flow-receipts'
```

Each entry names the one before it, which is how Flow notices a record that was edited or cut short:

```sh
jq -r '[.recordedAt, .previousDigest, .entryDigest] | @tsv' 'Plan.md.flow-receipts'
```

### The night record

One JSON object with a list of parts: which job wrote each change, the text before and after, when, and your decision.

```sh
jq '.parts[] | {job, at, review: (.review.state // "unreviewed"), before: .span.before, after: .span.after}' 'Plan.md.flow-night'
```

### Proposed changes and drafts

A JSON object each. The review file lists every proposal with its effect and your decision; the draft names the action, the section and the sources it read.

```sh
jq '.packets[] | {effect, decision}' 'Plan.md.flow-review'
```

```sh
jq '{savedAction, section, sources: [.sources[].path]}' 'Plan.md.flow-draft'
```

## Keys in a document's front matter

These sit between the `---` lines at the top of a document. They are meant to be read and edited; the Jobs and Definition controls write the same keys.

| Key | What it says | Edit it? |
| --- | --- | --- |
| `jobs:` | The work Flow repeats for this document | Yes |
| `refresh:` | When bound tables and charts redraw: `as-data-changes`, `overnight` or `manual` | Yes |
| `last-updated:` | When the Night Shift last changed the document, and from what | Flow rewrites it after each change |
| `publish:` | Where and how the document publishes: `formats`, `repository`, `domain`, `url`, `theme`, `pages-navigation`, `pdf-navigation`, `cover`. Flow reads a block you write here; File ▸ Publish remembers its choices in `Plan.md.flow-publish` instead, so publishing never changes the document | Yes |

A `jobs:` block is a list. Each item starts with `- kind:` and adds the fields that kind needs:

```yaml
jobs:
  - kind: keep-sources-fresh
    watch: [notes/supplier.md, https://example.com/pricing]
  - kind: reconcile-against-folder
    folder: invoices
  - kind: refresh-from-data
  - kind: gather
    definition: Budget Refresh.md
    into: data
    as: capture
  - kind: overnight-notes
  - kind: expand-with-sources
    section: Background
    sources: [research/interview.md]
    length: 300
```

| Kind | Fields |
| --- | --- |
| `keep-sources-fresh` | `watch:` files in the folder, or `https` pages |
| `reconcile-against-folder` | `folder:` the folder to list |
| `refresh-from-data` | none; redraws every bound table and chart |
| `gather` | `definition:` the saved definition; `into:` (default `data`); `as:` (default `capture`) |
| `overnight-notes` | none |
| `expand-with-sources` | `section:`, `sources:`, `length:` in words |
| `summarize`, `proofread`, `visualize`, `text-to-table`, `describe-picture` | `section:` |
| `translate` | `section:`, `language:` |
| `table-to-text` | `section:`, `shape:` |
| `run-script` | `script:`; older documents only, no longer offered |

Every kind also accepts `cadence: nightly`, and the model-backed kinds accept `reasoning:`. A document holds at most one of the AI actions (`expand-with-sources` through `table-to-text`) as a Job.

## Bound tables and charts

A table or chart that redraws from data names its data where it stands, not in the front matter: on a chart's opening line, or in a comment just above a table. It is the one place Flow adds its own words inside a document's body, because the binding belongs to that one block.

````markdown
```chart data: data/capture-*.json#summary
...
```

<!-- data: data/spending-*.json#rows -->
| Category | Amount |
| --- | --- |
````

The path is relative to the document. A `*` in the file name picks the newest match by name. After `#`, a key picks rows from a JSON file; `#table:Heading` reads the one table under that heading in a Markdown file, and `#tables:Heading` reads it from every match. A redraw rewrites only the chart's `data:` list or the table's rows; the heading, the header row and your prose stay as you wrote them.

Two more blocks are written by Jobs and read like any Markdown: a `flow-folder` block, the table of files a folder Job lists, and text between `<!-- night: notes -->` and `<!-- /night: notes -->`, the overnight notes.

## Gather definitions and captures

A `gather` Job names a definition document. Its front matter has four parts, in this order: `sources` (files, file patterns or `https` pages to read), `derive` (steps such as `filter`, `calculate`, `aggregate`, `sort`), `let` (named values) and `emit` (what to save). Open it with **File ▸ Edit Definition…**, or edit the keys directly.

Each run saves a capture: `data/capture-2026-09-27.json`, named by the Job's `into:` and `as:` and the date. It is ordinary JSON with the date, the files it read, and the rows it emitted:

```sh
jq '{capturedAt, source}' data/*.json
```

## Saved versions

Version history is ordinary git. If the folder is already a git repository, Flow keeps its versions there on its own line, `refs/flow/history`, and never commits to your branches. If the folder has no git repository, Flow creates one, keeps its versions on that line, and leaves `main` empty for you. If the folder sits inside another repository, Flow keeps its versions in a `.flow-history` folder so it never writes into the outer one.

Every saved version of `Plan.md`, newest first, with who wrote it:

```sh
git log --format='%h %an %ad %s' refs/flow/history -- 'Plan.md'
```

The latest saved text; put a version from the list in place of `refs/flow/history` for an older one:

```sh
git show refs/flow/history:'Plan.md'
```

In a folder that uses `.flow-history`, add `--git-dir=.flow-history`:

```sh
git --git-dir=.flow-history log --format='%h %an %ad %s' refs/flow/history
```

The author names the writer: `Flow` for versions you saved, `Flow Night Shift` for the Night Shift's changes, the assistant's name for an AI change, and the other app's name for a change made outside Flow. Each version also carries the details of its entry in the record of changes, which `git cat-file -p` shows beside the author.

**A clone or a push does not carry these versions**, because they are not on a branch. To copy them to another repository, fetch the line by name: `git fetch <source> '+refs/flow/*:refs/flow/*'`.

## What Flow keeps outside the folder

Some things are about you or your Mac rather than a document, so they stay out of your folders: your settings, including the Night Shift's schedule, and your folder list in Flow's preferences; API keys, your licence and publishing credentials in the Keychain; the Night Shift's last run and working state, downloaded models and usage counts in Flow's Application Support folder. None of them is needed to read your documents.
