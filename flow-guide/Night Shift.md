---
title: Night Shift
tags: [flow, start-here, night-shift]
---
# The Night Shift

The moon in the title bar is the Night Shift: Flow working on your documents
while you sleep, and showing you exactly what it did in the morning. On
every plan it does the patient, checkable work: fetches the pages you named,
reads the files you named, redraws the charts and tables you bound to them,
keeps the folder inventories current, and writes a Morning Briefing with the
exact diff of everything that moved. With a Flow plan it can also write a few
sentences about what the page's numbers say, on a model on this Mac, with
every number checked against its source before a sentence is kept.

![A quiet desk, work waiting for the morning](assets/quiet-desk.jpeg)

## A living document

Any document becomes a living document by carrying a `jobs:` list in its
front matter, or a chart or table drawn from a file. Nothing else creates
one: no folder is watched, no page is fetched, no file is rewritten unless a
document you wrote says so.

```yaml
---
title: Portfolio Dashboard
jobs:
  - kind: keep-sources-fresh
    watch: [Holdings.md, data, https://www.federalreserve.gov/newsevents/pressreleases.htm]
  - kind: reconcile-against-folder
    folder: data
---
```

| Job | What the night does | What you see in the morning |
| --- | --- | --- |
| `keep-sources-fresh` | Takes a snapshot of each file, folder or public `https` page in `watch` and compares it with the night before. A page is compared by its text, not its markup. | The exact diff of each source that changed, and the name of any that could not be read. Writing a URL into `watch` is the consent to fetch it nightly; every fetch has a receipt. |
| `reconcile-against-folder` | Lists the named folder and rewrites the document's inventory of it: name, size, modified date and a short digest, in a fenced block that reads as a table. | The inventory current, and the new or changed files named. |
| *(the redraw — no row needed)* | Redraws every chart whose opener says `data: <file>` and every table under a `<!-- data: <file> -->` comment from the file it names, rewriting only the rows. The binding is the declaration: a document with such a block is a living document with nothing else written. A `refresh-from-data` row from an older document is still accepted and means the same thing. | The chart or table current, and its redrawn shape copied into the Briefing as the snapshot. |
| `gather` | Reads the sources a definition document names — files beside the page, or `https` pages it lists — shapes them by the definition's steps, and writes the capture the data refresh redraws from. The definition is a document you read as data; nothing of yours runs. | The capture named in the Briefing's account, and every chart and table redrawn from it. |
| `overnight-notes` | **The one job a model does.** After the redraw, writes a few sentences about what the page's tables and charts say and what moved, between two marks the document carries under *Overnight notes*. The model sees the page's own numbers and nothing else of the document; every number in its draft is checked against a source row, once more if one is missing, and a draft that still names a number no row carries is withheld and the morning says which. Runs on a model on this Mac. Part of a Flow plan. | The notes marked in place like any other change, kept or reverted on Review Changes; the Briefing names the model and how many numbers were traced, or why nothing was written. |

Every job in this table but the last is deterministic: the same declaration
over the same data writes the same bytes, and no model takes part in any of
them. `overnight-notes` is the one that is not, and it says so where it is
offered. One older row, `run-script`, is still accepted from a document that
carries it and makes no such claim, because what runs there is yours; Flow no
longer offers it, and no document in this Guide uses one. A gather definition
says what a script used to.

Paths are relative to the document. A `*` in a file name takes the newest
capture by name; `#key` names the list inside a JSON file or a Markdown
file's front matter; a pattern like `updates/*.md` with no key reads one row
per file. Unchanged data leaves the document untouched.

**You never have to type the block by hand.** Under a document's title, the
*Night Shift* line ends in *Edit…*, which opens the Jobs Editor: add a job,
remove one, change what it does, choose its folder or its definition, and
Save. For a document with no jobs yet, File ▸ *Night Shift Jobs…* opens the
same editor. A block Flow could not read opens it in a repair state that
names the line and offers Source, or replacing the block on your word. Adding
*Overnight notes* there also offers to add the section the notes go in, once,
at the end of the document.

## The morning

Flow keeps a **Morning Briefing** in this folder, rewritten on every night
the shift ran: one section per living document that changed, ranked, with
the snapshot and two buttons, *Open* and *Review*. The Ideas board shows one
card per document with unreviewed changes. Open the document and each change
is marked in place; *Review* lists them with **Keep** and **Revert** per
change, and every applied change is a receipt in the Receipts pane and a
version in History. An empty Briefing is an honest morning: the shift ran,
nothing moved.

## Turning it on

The moon in the title bar, or **Settings ▸ Night Shift**. The first shift
runs while you watch, so you see a morning before there has been a night. The
shift runs in a window you choose, 02:00 to 06:00 by default, only when the
Mac is plugged in and idle; if the Mac sleeps through the window, it catches
up at the next wake and says so. Nothing runs on battery.

## What every plan gets, and what a plan adds

Night Shift Base is every deterministic job above, the Briefing, and Review
Changes, on every plan, day or night. Night Shift Pro is *Overnight notes*:
the one job that asks a model, which is what a Flow plan buys. A document that
declares the notes on a Base plan still gets every other job, and its
Briefing line says the notes are part of a plan.

## What never happens

- No text of yours is sent anywhere. The only network traffic is the `https`
  pages you listed in `watch`. *Overnight notes* run on a model on this Mac,
  and a night whose only model would be elsewhere writes no notes and says
  so; a local pass costs nothing to run.
- No document without a `jobs:` block is touched.
- Every write is a night version you can revert, with a receipt naming the
  run.

## Six living documents, ready to make yours

Each folder below is a complete case: a dashboard bound to data, a profile
file whose front matter you edit, a folder the night inventories, and a note
on how the page is built so you can lift any construct into your own work.

| Folder | The living document | Edit this | Where the numbers come from |
| --- | --- | --- | --- |
| Stock Portfolio | [[Portfolio Dashboard]]: ten widely held stocks priced at the close, allocation, a month against the S&P 500, candlesticks, a gains bridge, macro indicators, headlines | [[Holdings]] | A gather definition, [[Portfolio Refresh]], read before the page redraws |
| Tax Advisor | [[Tax Advisor]]: the federal year, an estimate from your W-2 forms, the standard-or-itemized call, headroom in the tax-advantaged accounts, deadlines, the IRS pages watched for changes | [[Tax Profile]] and `inputs/` | A gather definition, [[Tax Refresh]]; the forms table and the watches read the folder directly |
| Household Budget | [[Household Budget]]: the month against the plan, categories against budgets, merchants, the lines no rule caught | [[Budget Profile]] and `statements/` | A gather definition, [[Budget Refresh]], which reads the statements |
| Job Search | [[Job Search]]: applications on a timeline, the tracker, prep, careers pages watched, resume versions on record | [[Applications]] | The folder itself |
| Competitor Watch | [[Competitor Watch]]: entry prices, the feature matrix, pricing pages watched nightly | [[Competitors]] | The folder itself |
| Team Status | [[Team Status]]: one file per person rolled up into a table, a confidence chart and the quarter's timeline | `updates/` and [[Plan]] | The folder itself |

Four of the folders, the Starter among them, collect their numbers from a
**gather definition**: a document you can read, listing where each figure
comes from and how it is shaped. Flow reads it before the page redraws. No
script runs, so there is nothing to allow and nothing to trust. The other
three folders read their own folder directly.

**To start your own, copy the seventh folder.** [[Living Document]] in
*Living Document Starter* wires every construct once, a key-value table, a
table and two charts from one list, a one-row-per-file table over a folder,
two charts from a data capture, the inventory and a watched page, each with a
note on where it reads from, beside a [[Profile]] to rename, an example
entry, and a gather definition to copy, which names its source and the shape
it reads. Duplicate the folder, rename it, delete
what you do not need.

## Overnight notes

Every living document in this Guide declares `overnight-notes` and carries
the section it writes into:

```markdown
## Overnight notes
<!-- night: notes -->
<!-- /night: notes -->
```

The night rewrites only what lies between the two marks. What it writes from
is the page as it stands after the redraw: each bound chart and table under
its heading, the diff of each watched source that moved, and the notes as
they stood, so the model rewrites rather than restarts. A number the draft
names that no row carries is asked for once more by name, and withheld after
that, with the number in the Briefing. Numbers that moved since the notes
were last written count as untraced, so the notes are rewritten when the
data moves and left alone when it does not.
