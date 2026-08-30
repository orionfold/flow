---
title: Changelog
tags: [flow, start-here, whats-new]
---

# What is new in Flow

Newest release first. Every release names what shipped, how it benefits you,
and how to use it. Your Flow's version is in the title bar and in
Settings ▸ Flow System. This document travels with the Guide: **Settings ▸
Flow System ▸ Flow Guide Updates…** fetches the newest copy, so a Flow one
release behind can still read what the next one brought.

| Release | Build | Date | In a sentence |
| --- | --- | --- | --- |
| 1.5.6 | 1563 | 29 August 2026 | The first week, second pass: the small things, and dictation that can hear you |
| 1.5.5 | 1526 | 29 August 2026 | Know what Flow does with your network, and be able to show it |
| 1.5.4 | 1511 | 28 August 2026 | Your own files and folders: Flow keeps up with changes made outside it |
| 1.5.3 | 1446 | 28 August 2026 | The small things you meet in your first week |
| 1.5.2 | 1414 | 27 August 2026 | A pressable Update ready button |
| 1.5.1 | 1404 | 27 August 2026 | The first Flow that arrived through Flow itself |
| 1.5 | 1382 | 26 August 2026 | The launch |

## Flow 1.5.6 · build 1563 · 29 August 2026

This release is the second pass over the first week: the small frictions you
meet while actually working, and one thing that never worked at all.

### Dictation can hear you

- **What shipped.** Pressing the microphone starts dictation. On every Flow
  from 1.5 to 1.5.5 it opened System Settings ▸ Privacy & Security ▸
  Microphone instead — where Flow was already switched on — because the
  signed app had never declared that it records audio, so macOS refused
  before it could even ask you.
- **How it benefits you.** Speaking into a document works, and the first
  press asks for the microphone the ordinary way instead of sending you to a
  settings pane that looked correct already.
- **How to use it.** Open a document in the Editor and press the microphone
  in the toolbar, or ⇧⌘D. Allow the microphone when macOS asks. Speech stays
  on this Mac.

### A Guide update reaches the document you have open

- **What shipped.** After *Flow Guide Updates…* brings new text, a tab
  already showing that document reloads at once. It used to keep the old text
  until you closed and reopened it. A document you are part-way through
  editing is never reloaded under you.
- **How it benefits you.** You read what you just pulled, where you were
  already looking.
- **How to use it.** Settings ▸ Flow System ▸ Flow Guide Updates…

### A document that arrives from outside is marked new

- **What shipped.** Drop a file in from Finder, write one from the terminal,
  or pull a branch: when Flow re-reads the folder, the new document's sidebar
  row wears the same orange triangle a tab wears when its file changed on
  disk, until you open it. Your own renames, duplicates and new documents are
  never marked.
- **How it benefits you.** You can see what arrived without comparing the
  sidebar against your memory of it.
- **How to use it.** Switch back to Flow, or press ↻ in the Folders header.

### Tables and quotations read properly

- **What shipped.** A table column is now at least as wide as its longest
  word, so an address like `orionfold.supabase.co` or a heading like *Today*
  is never split down the middle; a table wider than the pane scrolls
  sideways inside its own frame. A `>` quotation written over several lines
  now joins with one space, like a paragraph, instead of showing a gap at
  every line end.
- **How it benefits you.** Documents you did not write — pasted tables,
  quoted decisions — read as their author meant them to.
- **How to use it.** Nothing to set.

### Split Right and Combine Panes are ⌥⌘] and ⌥⌘[

- **What shipped.** The two pane commands moved off ⌘] and ⌘[, which indent
  and outdent in the Editor as they do in every code editor. With a document
  focused the old chords never reached the menu at all.
- **How it benefits you.** Splitting a pane works while you are writing, and
  indenting still works where you expect it.
- **How to use it.** ⌥⌘] splits right, ⌥⌘[ combines. The Window menu shows
  both.

### The AI actions say more, and say it once

- **What shipped.** The *Leaves this Mac* sheet lists every item it counts —
  *2 items* now has two rows, your instruction and the document by its name —
  and names the model the way the hover panel does (*Claude Opus 5*, not an
  identifier). Proofread's *N words* and the status bar's count are now the
  same number; the panel used to count the front matter too. Settings ▸ Cost
  carries one caption instead of two sets of numbers, and before your first
  *Refresh OpenRouter prices* it says why those columns are empty and names
  the button. Flow still never fetches prices on its own.
- **How it benefits you.** What a run will send, what it will cost, and what
  it will read all say the same thing as each other.
- **How to use it.** Press any AI action and read the panel before you
  approve it; Settings ▸ Cost compares every model you can run.

## Flow 1.5.5 · build 1526 · 29 August 2026

This release is about knowing what Flow does with your network, and being
able to show it. Nothing new leaves your Mac in this release: Flow reaches no
address it did not reach before.

### The Flow Guide lists every time Flow reaches out

- **What shipped.** [[Working With Flow]] gained a section, *What leaves your
  Mac*, with a row for each connection Flow can make: when it happens, where
  it goes, what is sent, and the switch that turns it off. It also says what
  Flow never does. No usage statistics. No crash reports. No analytics or
  advertising code. No hidden number that identifies your copy. No online
  check to keep working.
- **How it benefits you.** "Does my text leave my Mac?" now has a printed
  answer you can read, check against Settings, and show to anyone who asks,
  instead of a promise.
- **How to use it.** Open [[Working With Flow]] and scroll to *What leaves
  your Mac*. Every row names its switch; most of them are a domain switch in
  Settings ▸ Models.

### Copy Diagnostics

- **What shipped.** *Help ▸ Copy Diagnostics…*, also in Settings ▸ Flow
  System under *Feedback*, writes a short block for a bug report and puts it
  on your clipboard: your Flow and macOS versions, the kind of Mac you have,
  which domains are switched on, which local runtimes are serving, and a
  count of any crashes in the last week. No file paths, no document titles,
  no names.
- **How it benefits you.** A report carries the facts that help, in one
  paste, and you decide where it goes. Flow shows you the exact text first,
  sends nothing, and the block goes only where you paste it.
- **How to use it.** Help ▸ Copy Diagnostics…, read the sheet, press Copy.
  Then *Issue or Feature Request* (in Help, or in Settings ▸ Flow System)
  opens a new issue with your Flow version already filled in. Paste the block
  under it.

## Flow 1.5.4 · build 1511 · 28 August 2026

This release is about your own files and folders. Flow keeps up with changes
you make outside it.

### Folders stay current

- **What shipped.** A file you add or change outside Flow shows up when you
  switch back. A **Refresh** button beside the sort control in the Folders
  header re-reads every open folder on one click, and turns once so you can
  see it ran.
- **How it benefits you.** Write a note from the terminal, drop one in from
  Finder, pull a branch: the document is in the sidebar and in search when
  you come back. No relaunch.
- **How to use it.** Switch back to Flow, or press ↻ in the Folders header
  (⌘1 shows Folders).

### A folder's menu is its whole menu

- **What shipped.** Right-clicking a folder offers everything its ⋯ menu
  does: New Document, New Folder, Pin Folder, Reveal in Finder, Copy Path,
  Close All Files, Remove Folder. Copy Path is new for folders.
- **How it benefits you.** One menu, whichever way you open it, and the full
  path of any folder in one click.
- **How to use it.** Right-click a folder row in Folders, or press its ⋯.

### Documents open where you left them

- **What shipped.** A document comes back on the view it was closed in,
  Source, Editor or Reader, whether you open it from the sidebar, Recents, a
  search hit, or after a relaunch. An empty file opens in the Editor. A new
  document (⌘N) or a reopened one has the cursor ready. Source view sits on
  the same centred column as Reader and Editor. Nothing is written into the
  file for any of this.
- **How it benefits you.** No re-choosing the view, no click before you can
  type, and no sideways jump when you switch views with ⌥⌘/.
- **How to use it.** Nothing to set.

### Deleting a saved document asks first

- **What shipped.** Delete confirms even for a saved document — *This moves
  the document to the Trash. You can put it back from there.* — with one
  **Move to Trash** button. A document with unsaved edits keeps its stronger
  Save / Discard prompt, and the two never read alike.
- **How it benefits you.** Nothing is trashed on one click.
- **How to use it.** Right-click a document in the sidebar ▸ Delete.

### Fewer surprises from the AI actions

- **What shipped.** Expand says how big the draft will be, *25 → about 300
  words* on the panel and *Expands to about 300 words* on the Leaves this Mac
  sheet, and that is the size the model is asked for. A long proposal shows
  in full in Review Changes. Removing a model from a provider (`ollama rm`, a
  replaced Flow Runtime import) no longer switches that provider off in Smart
  Routing; Settings shows the missing model as *(not available)* so you can
  pick another.
- **How it benefits you.** You know the size before you approve the run, a
  long review reads as a document rather than as Markdown source, and a
  provider keeps working when one of its models goes away.
- **How to use it.** Select text and press **Expand** on the document
  toolbar; the estimate is on the panel before anything runs.

### Charts and the toolbar

- **What shipped.** Long category names on a chart shorten with an ellipsis,
  and the full name shows on hover. A chart's hover label clears the moment a
  toolbar panel or menu opens over it. Every document toolbar tool, Bold to
  the microphone, shows a panel on hover saying what it does, where the
  result lands, and how to undo it. Dictation's panel says that speech stays
  on this Mac.
- **How it benefits you.** Charts stay readable with long labels, and you
  learn each tool where it sits.
- **How to use it.** Hover a bar. Hover a toolbar button.

## Flow 1.5.3 · build 1446 · 28 August 2026

This release cleans up the small things you meet in your first week with
Flow.

### Reviews are honest about size

- **What shipped.** When a model's reply matches your text except for line
  endings, a trailing newline, or spaces at the ends of lines, the run says
  **no changes needed** instead of opening an empty review. Proofread,
  Summarize, Translate and Expand now end with what actually moved — *Changed
  2 words of 3,900* — counted from the proposal itself.
- **How it benefits you.** No empty review to inspect, and a small real
  correction in a long document is named rather than lost.
- **How to use it.** Nothing to set. Read the sentence at the top of Review
  Changes.

### Receipts read plainly

- **What shipped.** A run on your Mac says *This run was free — it ran on
  your Mac*, and a measured zero reads `$0.00`. The Provider row names Flow
  Runtime, Ollama or LM Studio. A chart, summary, translation or table run
  reads *Evidence · Not scored*. A string of autosaves folds into one
  *Document saved N times* row that opens to the versions. After Approve &
  Save, the Receipts tab lands on the run that just happened, and the *Chart
  ready — review…* banner closes with the review's decision.
- **How it benefits you.** The record reads the way you would say it, and the
  run you just approved is the one in front of you.
- **How to use it.** Open a document's Receipts tab.

### Smaller fixes

| What shipped | How it benefits you | How to use it |
| --- | --- | --- |
| A highlight from search, a review or Ideas clears on your next click outside it, or on Escape | The thing Flow showed you stops glowing once you move on | Click on the highlight itself to keep it: that is you putting your cursor there |
| The first heading no longer shows a raw `#` when a document opens | The page reads as a page from the first frame | Nothing to set |
| The notice about local models that need a Flow Runtime version can be closed | Closed means not now; it stays closed across launches | Press its ×; it returns only when a different model is refused |
| Insert Image and Insert Chart or Diagram grey out when the focused tab has no document | A Format command never fails silently | Focus a document tab and they come back |
| The chart hover bubble leaves when your pointer does | No value stuck on the page | Move the pointer off the bar |
| Issue or Feature Request opens a new issue with your Flow version filled in | A report says which Flow it came from | Help ▸ Issue or Feature Request, or the same item in the sidebar and in Settings |

## Flow 1.5.2 · build 1414 · 27 August 2026

### Update ready is a button

- **What shipped.** When a newer Flow is waiting, the title bar shows a teal
  **Update ready** button with a download icon, to the right of the version
  it will replace. The plan pill now states your plan and nothing else.
- **How it benefits you.** You can see that an update is waiting, and press
  it. Before, the words sat as plain text inside the plan pill with nothing
  to press.
- **How to use it.** Press **Update ready** to read what changed and
  install. Flow ▸ Check for Updates… checks right now, any time.

## Flow 1.5.1 · build 1404 · 27 August 2026

### The first update that arrived through Flow

- **What shipped.** The first Flow delivered by Flow itself: no download, and
  nothing to drag into Applications. Flow also writes the outcome of every
  update check to the system log, so if a check ever fails there is a reason
  to read instead of a guess.
- **How it benefits you.** Every update from here on arrives the same way.
  Press **Install Update** and Flow restarts on the new version with your
  documents, settings and receipts exactly where they were.
- **How to use it.** Flow looks for a new version at launch and then at most
  once every six hours. Settings ▸ Flow System says which version you are on
  and what the last check found; Flow ▸ Check for Updates… runs one by hand.

## Flow 1.5 · build 1382 · 26 August 2026 · the launch

Flow is a native Mac app for professional documents with AI agency built in.
It works on ordinary folders of plain Markdown files: AI proposes each change,
you approve it, and the record stays with the file. This is what the launch
release brought.

### See the change before it becomes yours

- **What shipped.** Seven AI actions — Proofread, Summarize, Translate, two
  table conversions, Expand with Sources, and Visualize — each proposing an
  exact diff in **Review Changes**. You can approve it, reject it, or keep
  reviewing. Your document changes only when you say so, and a change that
  fails one of your guardrails stays on the record if you override it.
- **How it benefits you.** Nothing is written without your approval, and you
  read the writing first and the decision after.
- **How to use it.** Open the document in the Editor (⌥⌘/ switches between
  Reader and Editor), select text, and press an AI tool on the document
  toolbar or choose it from the Agency menu.

### Turn plain text into finished visuals

- **What shipped.** 34 chart types and 20 diagram types drawn in place,
  offline, from readable text that stays in your file. A chart editor with
  the chart chosen by type, a Chart gallery that opens any chart in its own
  tab, pictures rendered in place with an image editor for the alt text, and
  **Visualize**, which asks Flow to turn a table, list or paragraph into a
  chart you review before it lands.
- **How it benefits you.** The picture lives in the Markdown. Any other
  editor still reads the same file.
- **How to use it.** Format ▸ Insert Chart or Diagram…, or the toolbar's
  Insert Chart. [[Visualization Gallery]] shows every kind Flow draws. Select
  a table and press Visualize (⇧⌘V).

### Choose where every model may run

- **What shipped.** Four domains, each with its own switch: Local, LAN,
  Cloud prepaid, Cloud postpaid. Flow Runtime is built in, so there is
  nothing else to install; models already in Ollama or LM Studio are found
  without copying them; OpenAI, Anthropic and OpenRouter run on your own key;
  Codex CLI and Claude Code subscriptions can run Flow's actions too. Smart
  Routing lets your rules pick the model, and the screen names the rule that
  decided. Benchmarks measures your local models on this Mac, and a fallback
  that would cross a boundary stops and asks first, with the estimated cost
  on the *Leaves this Mac* sheet.
- **How it benefits you.** Your text leaves this Mac only if you allow it,
  and you know the cost before you approve.
- **How to use it.** Settings ▸ Models (⌘4 opens Settings) for the domains,
  providers and keys; Settings ▸ Benchmarks to measure; Settings ▸ Smart
  Routing for the rules. The **Ideas** panel (⌘3) proposes only the setup
  this Mac actually needs, and nothing runs until you say so.

### Keep the proof with the work

- **What shipped.** Every approved run leaves a receipt with the model, the
  route, the cost, the checks, the evidence, and the revision you chose to
  keep. Guardrails can be set once and adjusted per document. Version History
  shows every saved revision and lets you restore one.
- **How it benefits you.** The record stays with the file instead of
  disappearing with a chat session, and a difference between two versions
  says when it cannot be fairly compared.
- **How to use it.** A document's Receipts tab; ⇧⌘Y for Version History;
  Settings ▸ Guardrails for the rules.

### The document is the workplace

- **What shipped.** Folders of Markdown you already own, with no import step
  and no private format. Editor, Reader and Source views; search across every
  open folder, by words and by meaning; tabs, panes and split view; Recents;
  wiki links and backlinks; tables with a grid view; footnotes; dictation
  that stays on this Mac; and this Guide, opened side by side with Ideas on
  first launch. Reading, writing, searching, organising and exporting are
  free forever. Pro adds the AI, with 10 Pro Days included to start.
- **How it benefits you.** Other apps read the same files. Deleting a file
  sends it to the system Trash. If a subscription ends, the AI stops and the
  documents remain open and editable.
- **How to use it.** Add Folder in the sidebar; ⌘N for a new document; ⌘] to
  split; ⇧⌘F to search; ⇧⌘D to dictate.

### What the launch build fixed

Build 1382 replaced the day's first build, 1255, with the fixes the launch
walk found: a new document opens in the Editor with a caret; a table or an
Expand draft is written with a blank line either side so it renders in the
review and in the saved file; a chart proposed on a document open in the
Editor draws; Settings ▸ Flow System says *Flow is up to date* when there is
nothing newer; Settings keeps equal margins in a split pane on a 14" MacBook
Pro; the *Leaves this Mac* sheet says what its estimate prices; the editor
toolbar carries Insert Image and Insert Chart; and choosing a picture lands
you on the document that received it.
