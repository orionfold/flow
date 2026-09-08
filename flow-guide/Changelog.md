---
title: Changelog
tags: [flow, start-here, whats-new]
---

# What is new in Flow

Newest release first. Every release names what shipped, how it benefits you, and how to use it. Your Flow's version is in the title bar and in Settings ▸ General. This document travels with the Guide: **Settings ▸ General ▸ Flow Guide Updates…** fetches the newest copy, so a Flow one release behind can still read what the next one brought.

| Release | Build | Date | In a sentence |
| --- | --- | --- | --- |
| 1.6.3 | 2017 | 7 September 2026 | The point release after the first Night Shift week: documents from other tools open whole, the Reader and the Editor read the same page, and every Settings sentence says what is actually so |
| 1.6.2 | 1994 | 6 September 2026 | Every number about tokens and money is one number, read from your documents' own receipts — the night's work counts where the day's does |
| 1.6.1 | 1982 | 6 September 2026 | The first day with the Night Shift: pause and stop a run, a Briefing that reads true the morning after, and a lighter night |
| 1.6 | 1899 | 5 September 2026 | The Night Shift: living documents that keep themselves current, and one Morning Briefing |
| 1.5.6 | 1563 | 29 August 2026 | The first week, second pass: the small things, and dictation that can hear you |
| 1.5.5 | 1526 | 29 August 2026 | Know what Flow does with your network, and be able to show it |
| 1.5.4 | 1511 | 28 August 2026 | Your own files and folders: Flow keeps up with changes made outside it |
| 1.5.3 | 1446 | 28 August 2026 | The small things you meet in your first week |
| 1.5.2 | 1414 | 27 August 2026 | A pressable Update ready button |
| 1.5.1 | 1404 | 27 August 2026 | The first Flow that arrived through Flow itself |
| 1.5 | 1382 | 26 August 2026 | The launch |

## Flow 1.6.3 · build 2017 · 7 September 2026

The week after the Night Shift shipped, spent on what the operator met while using it for real. A document saved by Windows or a sync client opens whole; the Reader draws lists, code, tables and diagrams the way a person would lay them out and the Editor now shows the Guide as the same flowing paragraphs; the night says beforehand which model it will use and what it will cost, and counts its work one way everywhere; the definition editor and the jobs panel say plainly what is missing and what to press; and Settings stops saying things that were not so, from the rule that "decided" to the row that said updates were only checked on request.

### A document from Windows or a sync client opens whole

- **What shipped.** A file saved with Windows line endings, as Windows tools and some sync clients write them, used to open as body prose with no title, no tags and no standing jobs, and its tables never lit *Edit Table*. Flow now reads such a document exactly as it reads one saved on a Mac, and a page it redraws overnight keeps the line endings it had. Handing Flow a folder from the command line or by dropping it on Flow now shows the window with the folder open, where it used to show a menu bar and nothing else.
- **How it benefits you.** The document a colleague sent from Windows, or one a sync client rewrote, is the same document in Flow: title, tags, jobs and tables all there. Nothing has to be re-saved first.
- **How to use it.** Open it. A table in such a document opens in the table pane read-only, as before.

### The Reader and the Editor read the same page

- **What shipped.** A code span or a wikilink that wrapped at a line end no longer leaves an empty pill at the margin or its punctuation alone on the next line. The continuation of a long bullet, task or numbered item hangs under the first line's text, in the Reader and the Editor. A long line in a code block wraps instead of scrolling on its own row. In a table drawn from data, a column of dates reads *9 Sep 2026*, a column of one-word statuses reads *Green*, a header such as `price_per_seat` reads as written, and a column of prose keeps a readable width so a wide table scrolls rather than stacking one word per line. A Mermaid drawing wider than the column stops shrinking where its labels would become unreadable and scrolls; a Sankey's name and value read apart; a C4 diagram fills its card. And every Flow Guide document is written one line per paragraph, so the Editor shows the same flowing text the Reader does.
- **How it benefits you.** A page reads the same in both modes, and a wide table or diagram stays legible instead of being squeezed. The Guide no longer looks ragged the moment you switch to the Editor.
- **How to use it.** Nothing to set up. An existing Guide receives the reflowed documents through Settings ▸ General ▸ *Flow Guide Updates…*; a document already open shows the new text after you reopen it.

### The night says what it will use, and counts its work one way

- **What shipped.** The moon's popover and Settings ▸ Night Shift carry two more rows, *Model* and *Cost estimate*, derived from the same routing the night will use: the model and the provider it runs on, and *$0* while the night stays on this Mac. The strip's *Last shift* row and the Morning Briefing's lead count the same things in the same words, documents worked and changes made. A run over two folders reads *Folder 2 of 2 · 15 of 21 documents* above the roster, so the second folder's list no longer looks like the first one starting over. A redrawn page's *last-updated* stamp names the capture whose new rows changed it.
- **How it benefits you.** You know before bed which model will work and whether it costs anything, and the morning's numbers agree wherever you read them.
- **How to use it.** Hover the moon for the popover, or open Settings ▸ Night Shift. Nothing to set up.

### The definition editor and the jobs panel say what is missing

- **What shipped.** A row set or table downstream of a web page reads *waits for prices, read at night; press Fetch now to see its rows today* instead of a fault. With no part chosen the preview says *Pick a part to see its rows* rather than spinning. A newly added step stays in the editor until its fields are filled, so the definition on disk is always one the night can run, and a draft that forgot to say which rows to count is completed from the definition's one source, with the caption saying so. In the jobs panel a job's title line is in the primary ink, web-page notes sit as one footnote under the rows, a file the folder does not hold is marked *Not found in this folder* as you commit it, and a bare name like *Holdings* means *Holdings.md*, as a wikilink does. Review Changes holds about five rows and scrolls with the selected change in view, and Keep and Revert no longer hold the window while they write. The definition editor's three columns keep their widths and the pane scrolls sideways on a 14" display.
- **How it benefits you.** A definition that is merely waiting for the night is not called broken, an unfinished step cannot reach the file, and a long list of changes no longer pushes the document out of view.
- **How to use it.** Press *Fetch now* on a page that is waiting; pick a part to see its rows; fill a new step before leaving it.

### Settings says what is actually so

- **What shipped.** Smart Routing names the rule that actually decided: a rule with nothing to order by, such as *Fastest measured on this Mac* before any speed has been measured, no longer appears as the decider. Choosing a model yourself is two steps, provider then model; a provider that is switched off says so once, the same model name under two providers is two rows, the line beneath reads *Using qwen3.6-27b on Flow Runtime*, and Flow remembers which provider you picked. Settings ▸ General reads *Checked every 6 hours, and when you ask*, with when the last check completed beneath. Under Models, *What it costs* names the day Flow's price table was last read from the providers' pages, and a rail of three figures beside it shows what you have spent this session, last night and all time, read from your documents' receipts; an *Imported* confirmation reads in quiet ink and orange stays for a refusal; a model imported from a pinned Hugging Face snapshot is named for the model, not its commit hash. A Settings pane can no longer be squeezed narrower than its column; past that point the pane row scrolls. After you edit a document by hand, the receipts pill's *Stale* tooltip says the receipts predate your save and what brings them current.
- **How it benefits you.** Every sentence on the Settings pages is one you can check against what Flow does, and the cost table carries its date so a rate that moved does not read like one that did not.
- **How to use it.** Settings ▸ Smart Routing ▸ *Customize* for the two-step picker; Settings ▸ Models ▸ *What it costs* for the dated table and the spend rail.

### What Flow is using, counted whole

- **What shipped.** The title-bar readout's memory and CPU now include the helpers Flow launched for a benchmark and a model still loading; the GPU figure shows *100%* in full and says *no Flow model running* or *includes Flow's model* beside it, since macOS reports the whole Mac; a disk cell shows how full the drive holding your models is; and a model imported from Ollama is named by the name you gave it, not its file's digest.
- **How it benefits you.** The number you glance at during a benchmark is the whole cost of the benchmark, and a GPU figure with no Flow model running is not mistaken for Flow's.
- **How to use it.** Hover the readout in the title bar. Nothing to set up.

### The small things

- **What shipped.** The table editor sizes its columns to their content and shares the pane's spare width; the chart editor's encoding pickers wrap onto a second row; a document's first line starts below the floating toolbar, so a full-width table or photo is never covered at its corner. The Ideas pane has the same header as a Settings page, a document card names the document without `.md`, the approval sentence says *It stays on this Mac, uses this Mac's time and battery, and costs no money*, and a measurement run from Settings ▸ Benchmarks lands the measure card in Ideas Done saying where it was done. A highlighted chart coloured by another field fades the other rows instead of turning every series grey. A copy of Flow built from source no longer lights *Update ready* for the release it is newer than.
- **How it benefits you.** Fewer moments where a control or a word is not where you expect it.
- **How to use it.** Nothing to set up.

## Flow 1.6.2 · build 1994 · 6 September 2026

One change, in the place you look to see what Flow is using. Until now the title-bar readout and its popup counted the day's runs but not the night's, and the Morning Briefing counted the night's from a different place, so the two could disagree. Now every run Flow makes — by day or by night, on a model on this Mac or a hosted one, whether or not you kept its reply — leaves one usage record on the document it ran on, and every number Flow shows about tokens and money is read from those records.

### One number for what Flow used

- **What shipped.** The readout's *this session* figures, the popup's totals and the Briefing's *billed* line are all read from your documents' own receipts. Each run writes one usage record when it ends: a hosted run records what the provider charged, whether or not you kept its reply; a run on this Mac records its token counts at no charge. The popup's totals now read *Tokens in open folders* and *Spent in open folders*, because that is what they count — every run recorded in the folders you have open — and they read *counting…* for the moment after launch while Flow reads the receipts.
- **How it benefits you.** What the night used shows where what the day used shows, and the number in the Briefing is the number in the popup: there is no second tally to drift. A run you declined still counts what the provider billed, so the money figure is the honest one. And a document's Receipts pane now carries its runs' usage beside its changes, so the cost of a page is on the page.
- **How to use it.** Hover the readout in the title bar for the popup. *Tokens this session* and *Spent this session* count from this launch; *Tokens in open folders* and *Spent in open folders* count every run in the folders open now — close a folder and its runs leave the total, open it again and they return. Nothing to set up.

## Flow 1.6.1 · build 1982 · 6 September 2026

This release is the first day of using the Night Shift for real. A run can be held and ended from the moon and looks held while it is; the Morning Briefing reads true the morning after and says less when a page changed throughout; a night over large files no longer fills memory, and the model it used is released when it is done. Around that, the small things a first day finds: a shift's last line and a refresh's are two lines, a saved version says who saved it, expandable rows in Settings open from their title, a new tab lands first, and a Candlestick chart draws its days.

### Pause and stop a running shift from the moon

- **What shipped.** While a shift runs, the moon's popup offers *Pause Run* and *Stop Run* in place of *Pause tonight*. Pause holds the shift after the document it is on: the moon and the popup say *Paused*, that row shows a pause mark, and the clock stands at the working time it reached. *Resume Run* carries on from there. Stop ends the shift after that document, keeping every change that landed: the moon says *Stopping* and names the document, both buttons rest, and the Briefing says which documents and folders the shift did not reach. A stopped shift's Briefing, receipt and *Last shift* line count only what it reached, as *Stopped at* the moment it ended.
- **How it benefits you.** A shift that starts at the wrong moment costs one click and nothing half-written.
- **How to use it.** Click the moon while a shift runs. *Pause tonight* returns when the shift ends.

### The Morning Briefing reads true the morning after

- **What shipped.** A run by day leads with its day, *Saturday at 11:30 PM*, and *Still to review* says *Flow made on Saturday*, so the page is right whenever you read it. When a watched page or file has most of its text rewritten, the Briefing says so in one sentence with the line counts and leaves both versions to the run's snapshots; a targeted change still shows its exact lines. The night receipt's tiles count in the right words: *1 open folder swept*, *7 data folders inventoried*.
- **How it benefits you.** The Briefing says what happened, not a diff to decode or a "today" that was yesterday.
- **How to use it.** Nothing to do. Open the Briefing from the moon, from Ideas, or from the Flow Guide folder.

### A shift's last line and a refresh's are two lines

- **What shipped.** *Last shift* on the moon's popup and in Settings ▸ Night Shift names the last shift. A document redrawn during the day, as its data changed, shows as its own *Last refresh* line beneath it, only while it is newer than the shift and did something, and it appears the moment the refresh ends.
- **How it benefits you.** A redraw at noon no longer erases what the night did from the place you look for it.
- **How to use it.** Hover or click the moon.

### A lighter night: flat memory, and the model let go

- **What shipped.** A shift over a folder holding large files, such as model weights, exports or media, used to grow Flow's memory by the size of those files; it now stays flat while it reads them. The local model the Night Shift served inside Flow is released when the shift ends, and by day a model nothing has asked for in fifteen minutes is released too; the next request loads it again.
- **How it benefits you.** A Mac that ran the night is the same Mac in the morning.
- **How to use it.** Nothing to do.

### The small things of a first day

- **What shipped.** A version you saved yourself, a revert or a restore, reads *Saved by You* in History and Receipts. Expandable rows in Settings, such as *On this Mac*, *Cloud* and *Manage models*, open from their title as well as their chevron, and *On this Mac* lists Flow Runtime first. A provider that cannot serve says what to do: *Enabled, but LM Studio is not running. Open it and load a model.* Settings ▸ Documents no longer says *Indexing* forever after a cut-short refresh. A document you open, or a tab you move, lands as the first tab. The Night Shift line under a title is one line that begins with the moon, with a pencil into the Jobs Editor, and the Jobs Editor's title fits one row. A Candlestick chart spreads its sessions across their dates again. Provider order no longer lists Claude Code and Codex CLI until the route they promise ships.
- **How it benefits you.** Fewer things to work around on the second day.
- **How to use it.** Nothing to do.

## Flow 1.6 · build 1899 · 5 September 2026

This release is the Night Shift. A document you keep current by hand becomes a living document: it says what it draws on, Flow works it while you sleep, and the morning tells you what moved, in words, with every change yours to keep or put back. Around it, Settings is six screens instead of eleven, a model on your Mac can look things up, and a hundred small frictions from the first week are gone.

### The Night Shift runs while you sleep, with Flow closed

- **What shipped.** Settings ▸ Night Shift turns it on and sets the window (2:00 to 6:00 AM to begin with). Every night in that window, whenever this Mac is plugged in and idle, Flow works your open folders, with Flow open or quit, and never twice in one night. A Mac that slept through the window catches up once at the next wake, and says so. A moon in the title bar says what the shift is doing at a glance: *Tonight 2:00 AM*, *Running*, *Paused*, or the first thing that would stop it and the way out.
- **How it benefits you.** The work happens on the machine's time, not yours, and only when the machine can afford it.
- **How to use it.** Settings ▸ Night Shift ▸ *Runs tonight*. Turning it on runs the first shift right away, while you watch, and opens the Briefing it wrote. Click the moon to run it now, pause tonight, or open the Briefing.

### One Morning Briefing, written in words

- **What shipped.** A night writes one *Morning Briefing* in the Flow Guide folder, with earlier mornings in its History. One section per document that changed: its link, one sentence in the document's own terms, the changed chart or table drawn as it is, and *Open* and *Review*. Then *Also changed*, what the day already redrew, *Still to review* for changes waiting on you, and *Unchanged* with the reason. When a page you watch changes, the Briefing shows the exact text that moved, with the page's markup stripped away. The whole night is told in one clock, and the Briefing's Receipts name each night.
- **How it benefits you.** You read what happened, not a log of it.
- **How to use it.** Open the Briefing from the moon, from Ideas, or from the Flow Guide folder in the sidebar.

### Keep or put back each change the night made

- **What shipped.** A document Flow changed overnight opens with a bar, *Flow changed 3 things overnight*, and each changed block framed on the page. *Review* shows one card per change: *Keep* records your decision in Receipts, *Revert* puts that block alone back to its earlier lines as its own version in History. A block you edited since is marked stale and points you to History. The night's changes retire an earlier run's changes to the same block, so the bar and the Briefing count the same night.
- **How it benefits you.** Nothing the night does is out of your hands, and nothing you decide is lost.
- **How to use it.** Press *Review* on the bar, or *Review* beside the document in the Briefing.

### Seven living documents ship in the Guide

- **What shipped.** Six complete cases, each a folder: **Stock Portfolio**, **Tax Advisor**, **Household Budget**, **Job Search**, **Competitor Watch** and **Team Status**. Each has one profile whose front matter you edit (add a stock, a W-2, a competitor, a teammate) and the night redraws the page from it. The seventh, **Living Document Starter**, is the one to copy for your own: every construct wired once with a note on where it reads from. A new **Night Shift** page explains the moon, the jobs, the morning, and what never happens.
- **How it benefits you.** A living document of your own starts from one that already works.
- **How to use it.** Flow Guide ▸ a folder ▸ its dashboard. Copy the Starter's folder, rename it, and edit three things: the profile's front matter, the files in `entries/`, and the headings.

### A chart or table drawn from a file redraws on its own

- **What shipped.** Bind a chart or table to a file with `data:` on its opening line and the night redraws it, touching only that block. No declaration is needed; the binding is the declaration. *Redraw as data changes* (on to begin with) redraws the document the moment the file changes, when you come back to Flow, when you use Refresh Folders, and after a night's own work; Flow remembers its last look across a quit, so a file that landed while Flow was closed is noticed as Flow opens its folders, before you touch anything. A document names the capture it is drawn from under its title.
- **How it benefits you.** Drop this morning's export into the folder and the page shows this morning's numbers.
- **How to use it.** Settings ▸ Night Shift ▸ *Redraw as data changes* for everywhere; *Redraws* in the panel under a document's title for one document.

### A document says what it does overnight, and you edit it in a sheet

- **What shipped.** Under the title of any document with standing jobs, a line reads *Night Shift · Watches 3 sources · Lists the files in data · Redraws 4 charts and 3 tables from data/capture-*.json*. Open it and each job has its own line with Flow's explanation, a (−) on every line, and the setting it follows. *Edit…* opens the Jobs Editor: each job is a card chosen from what a job can be, watching sources, listing a folder's files, collecting data, or Overnight notes, with every field explained; Save writes once, Cancel writes nothing, and a block Flow cannot read still gets its Night Shift line, naming the line it could not read, whose *Edit…* opens a repair state.
- **How it benefits you.** A living document explains itself to whoever opens it next, and nobody edits front matter by hand.
- **How to use it.** *Edit…* on the Night Shift line, or File ▸ *Night Shift Jobs…* (⌥⌘J) on a document that declares nothing yet.

### A living document gathers its own data from a definition, not a script

- **What shipped.** A collecting job reads a definition written in plain front matter, which files, folders and web addresses to draw on, what to work out, and which tables to build, and writes the nightly capture the charts read. It runs nothing and asks for no permission to run anything: the definition is data you can read. The definition editor shows it as forms with a live preview of the rows, computed from your files the way the night computes them; a change is written the moment the whole definition reads. And a definition can be drafted from a sentence: describe what to gather, press *Draft*, and a model on this Mac proposes the sources, values and tables, shown in the editor before anything is written; *Use this draft* writes it, *Discard* leaves the file as it was.
- **How it benefits you.** The refresh a document depends on is something you can read, change and keep, with no Terminal and no code.
- **How to use it.** *Edit definition…* under a definition's title, or File ▸ *Edit Definition…* (⌥⌘D). *New…* in the Jobs Editor copies the Starter's definition beside your document.

### Night Shift Pro: Overnight notes, the one job a model does

- **What shipped.** After the night's redraw, a model on this Mac writes a few sentences about what the page's tables and charts say and what moved, under *Overnight notes*. The model sees the page's own numbers and nothing else of the document; every number in its draft is checked against a source row, and withheld with the number named if it cannot be. A note the model stops mid-sentence is cut back to its last whole sentence, or withheld with the reason in the Briefing. The notes are marked in place, kept or reverted on Review Changes, and receipted with the model that answered. Every other job runs on every plan; a Base plan's Briefing says the notes are part of a Flow plan.
- **How it benefits you.** The morning reads like a note from a colleague who checked the numbers, and every number in it traces to a row.
- **How to use it.** Add *Overnight notes* in the Jobs Editor; one Save writes the job and the section the notes go in. A model on this Mac is required; nothing leaves it.

### Settings is six screens

- **What shipped.** General · Documents · Models · Smart Routing · Evidence · Night Shift, down from eleven, with nothing removed: your plan at the top of General, saving and dictation under Documents, measured results and the price list inside Models, the three checks under Evidence's five questions. For a cloud provider the key is the switch: add a key and it is on, remove it and it is off, and a key exported in your login shell is found at launch. Smart Routing states Flow's tuning in one sentence, with Flow Runtime first. Models opens with this Mac and Flow's pick, and every local model that opens in Flow Runtime is shared with Flow the first time it looks. Web Lookups lives under General ▸ *What leaves your Mac*.
- **How it benefits you.** Every control is where its question is, and each thing is said once.
- **How to use it.** ⌘, opens Settings; searching it for an old screen's name still finds every control on its new screen.

### A model on your Mac can look things up before it answers

- **What shipped.** *Expand with Sources* reads your document and searches your folders before writing on a model that runs on this Mac, at no cost, with each lookup shown as it happens and recorded in the run's receipts; the same lookups run on OpenAI and OpenRouter as on Anthropic. A new switch, off to begin with, lets a run fetch a public web page, and the Guide's *What leaves your Mac* table lists it. A run a provider refuses says why and is recorded; the review pane lists what a run looked up; opening one lookup shows what it asked and what came back. A document that starts with front matter works on a cloud model, which is sent only the prose.
- **How it benefits you.** The answer is grounded in what you have, and every step of how it got there is on the record.
- **How to use it.** Agency ▸ *Expand with Sources*. Settings ▸ General ▸ *What leaves your Mac* ▸ *Web Lookups* to allow the web.

### The Guide keeps itself whole

- **What shipped.** A Guide update you accepted does not come back as a conflict; a Guide folder Flow lost track of, restored from a backup or synced from another Mac, repairs itself; a first launch completes a Flow Guide folder that was already there without replacing anything in it.
- **How it benefits you.** Updates arrive as updates, and what you wrote stays yours.
- **How to use it.** Settings ▸ General ▸ *Flow Guide Updates…*

### The small things

- **What shipped.** An escaped character reads as itself; a comment in a document stays out of the page; a wide table shows it scrolls; the scrollbar can be dragged from the top of a long document; a document still opening says *Opening…*; charts name their legends and axes in words and sideways bar charts label their bars; a note whose front matter carries a `#` comment opens; a document in a folder opened inside another folder works everywhere; OpenRouter is preferred over OpenAI and Anthropic when Flow picks for you; Flow's sentences lost their dashes and its explainers say each thing once.
- **How it benefits you.** Fewer things to notice, so you notice your work.
- **How to use it.** Nothing to do.

## Flow 1.5.6 · build 1563 · 29 August 2026

This release is the second pass over the first week: the small frictions you meet while actually working, and one thing that never worked at all.

### Dictation can hear you

- **What shipped.** Pressing the microphone starts dictation. On every Flow from 1.5 to 1.5.5 it opened System Settings ▸ Privacy & Security ▸ Microphone instead, where Flow was already switched on, because the signed app had never declared that it records audio, so macOS refused before it could even ask you.
- **How it benefits you.** Speaking into a document works, and the first press asks for the microphone the ordinary way instead of sending you to a settings pane that looked correct already.
- **How to use it.** Open a document in the Editor and press the microphone in the toolbar, or ⇧⌘D. Allow the microphone when macOS asks. Speech stays on this Mac.

### A Guide update reaches the document you have open

- **What shipped.** After *Flow Guide Updates…* brings new text, a tab already showing that document reloads at once. It used to keep the old text until you closed and reopened it. A document you are part-way through editing is never reloaded under you.
- **How it benefits you.** You read what you just pulled, where you were already looking.
- **How to use it.** Settings ▸ General ▸ Flow Guide Updates…

### A document that arrives from outside is marked new

- **What shipped.** Drop a file in from Finder, write one from the terminal, or pull a branch: when Flow re-reads the folder, the new document's sidebar row wears the same orange triangle a tab wears when its file changed on disk, until you open it. Your own renames, duplicates and new documents are never marked.
- **How it benefits you.** You can see what arrived without comparing the sidebar against your memory of it.
- **How to use it.** Switch back to Flow, or press ↻ in the Folders header.

### Tables and quotations read properly

- **What shipped.** A table column is now at least as wide as its longest word, so an address like `orionfold.supabase.co` or a heading like *Today* is never split down the middle; a table wider than the pane scrolls sideways inside its own frame. A `>` quotation written over several lines now joins with one space, like a paragraph, instead of showing a gap at every line end.
- **How it benefits you.** Documents you did not write, such as pasted tables and quoted decisions, read as their author meant them to.
- **How to use it.** Nothing to set.

### Split Right and Combine Panes are ⌥⌘] and ⌥⌘[

- **What shipped.** The two pane commands moved off ⌘] and ⌘[, which indent and outdent in the Editor as they do in every code editor. With a document focused the old chords never reached the menu at all.
- **How it benefits you.** Splitting a pane works while you are writing, and indenting still works where you expect it.
- **How to use it.** ⌥⌘] splits right, ⌥⌘[ combines. The Window menu shows both.

### The AI actions say more, and say it once

- **What shipped.** The *Leaves this Mac* sheet lists every item it counts: *2 items* now has two rows, your instruction and the document by its name. It names the model the way the hover panel does (*Claude Opus 5*, not an identifier). Proofread's *N words* and the status bar's count are now the same number; the panel used to count the front matter too. Settings ▸ Cost carries one caption instead of two sets of numbers, and before your first *Refresh OpenRouter prices* it says why those columns are empty and names the button. Flow still never fetches prices on its own.
- **How it benefits you.** What a run will send, what it will cost, and what it will read all say the same thing as each other.
- **How to use it.** Press any AI action and read the panel before you approve it; Settings ▸ Cost compares every model you can run.

## Flow 1.5.5 · build 1526 · 29 August 2026

This release is about knowing what Flow does with your network, and being able to show it. Nothing new leaves your Mac in this release: Flow reaches no address it did not reach before.

### The Flow Guide lists every time Flow reaches out

- **What shipped.** [[Working With Flow]] gained a section, *What leaves your Mac*, with a row for each connection Flow can make: when it happens, where it goes, what is sent, and the switch that turns it off. It also says what Flow never does. No usage statistics. No crash reports. No analytics or advertising code. No hidden number that identifies your copy. No online check to keep working.
- **How it benefits you.** "Does my text leave my Mac?" now has a printed answer you can read, check against Settings, and show to anyone who asks, instead of a promise.
- **How to use it.** Open [[Working With Flow]] and scroll to *What leaves your Mac*. Every row names its switch; most of them are in Settings ▸ Models: one switch for this Mac, and for a cloud provider the key itself.

### Copy Diagnostics

- **What shipped.** *Help ▸ Copy Diagnostics…*, also in Settings ▸ Flow System under *Feedback*, writes a short block for a bug report and puts it on your clipboard: your Flow and macOS versions, the kind of Mac you have, which domains are switched on, which local runtimes are serving, and a count of any crashes in the last week. No file paths, no document titles, no names.
- **How it benefits you.** A report carries the facts that help, in one paste, and you decide where it goes. Flow shows you the exact text first, sends nothing, and the block goes only where you paste it.
- **How to use it.** Help ▸ Copy Diagnostics…, read the sheet, press Copy. Then *Issue or Feature Request* (in Help, or in Settings ▸ Flow System) opens a new issue with your Flow version already filled in. Paste the block under it.

## Flow 1.5.4 · build 1511 · 28 August 2026

This release is about your own files and folders. Flow keeps up with changes you make outside it.

### Folders stay current

- **What shipped.** A file you add or change outside Flow shows up when you switch back. A **Refresh** button beside the sort control in the Folders header re-reads every open folder on one click, and turns once so you can see it ran.
- **How it benefits you.** Write a note from the terminal, drop one in from Finder, pull a branch: the document is in the sidebar and in search when you come back. No relaunch.
- **How to use it.** Switch back to Flow, or press ↻ in the Folders header (⌘1 shows Folders).

### A folder's menu is its whole menu

- **What shipped.** Right-clicking a folder offers everything its ⋯ menu does: New Document, New Folder, Pin Folder, Reveal in Finder, Copy Path, Close All Files, Remove Folder. Copy Path is new for folders.
- **How it benefits you.** One menu, whichever way you open it, and the full path of any folder in one click.
- **How to use it.** Right-click a folder row in Folders, or press its ⋯.

### Documents open where you left them

- **What shipped.** A document comes back on the view it was closed in, Source, Editor or Reader, whether you open it from the sidebar, Recents, a search hit, or after a relaunch. An empty file opens in the Editor. A new document (⌘N) or a reopened one has the cursor ready. Source view sits on the same centred column as Reader and Editor. Nothing is written into the file for any of this.
- **How it benefits you.** No re-choosing the view, no click before you can type, and no sideways jump when you switch views with ⌥⌘/.
- **How to use it.** Nothing to set.

### Deleting a saved document asks first

- **What shipped.** Delete confirms even for a saved document, saying *This moves the document to the Trash. You can put it back from there.* above one **Move to Trash** button. A document with unsaved edits keeps its stronger Save / Discard prompt, and the two never read alike.
- **How it benefits you.** Nothing is trashed on one click.
- **How to use it.** Right-click a document in the sidebar ▸ Delete.

### Fewer surprises from the AI actions

- **What shipped.** Expand says how big the draft will be, *25 → about 300 words* on the panel and *Expands to about 300 words* on the Leaves this Mac sheet, and that is the size the model is asked for. A long proposal shows in full in Review Changes. Removing a model from a provider (`ollama rm`, a replaced Flow Runtime import) no longer switches that provider off in Smart Routing; Settings shows the missing model as *(not available)* so you can pick another.
- **How it benefits you.** You know the size before you approve the run, a long review reads as a document rather than as Markdown source, and a provider keeps working when one of its models goes away.
- **How to use it.** Select text and press **Expand** on the document toolbar; the estimate is on the panel before anything runs.

### Charts and the toolbar

- **What shipped.** Long category names on a chart shorten with an ellipsis, and the full name shows on hover. A chart's hover label clears the moment a toolbar panel or menu opens over it. Every document toolbar tool, Bold to the microphone, shows a panel on hover saying what it does, where the result lands, and how to undo it. Dictation's panel says that speech stays on this Mac.
- **How it benefits you.** Charts stay readable with long labels, and you learn each tool where it sits.
- **How to use it.** Hover a bar. Hover a toolbar button.

## Flow 1.5.3 · build 1446 · 28 August 2026

This release cleans up the small things you meet in your first week with Flow.

### Reviews are honest about size

- **What shipped.** When a model's reply matches your text except for line endings, a trailing newline, or spaces at the ends of lines, the run says **no changes needed** instead of opening an empty review. Proofread, Summarize, Translate and Expand now end with what actually moved, *Changed 2 words of 3,900*, counted from the proposal itself.
- **How it benefits you.** No empty review to inspect, and a small real correction in a long document is named rather than lost.
- **How to use it.** Nothing to set. Read the sentence at the top of Review Changes.

### Receipts read plainly

- **What shipped.** A run on your Mac says *This run was free. It ran on your Mac*, and a measured zero reads `$0.00`. The Provider row names Flow Runtime, Ollama or LM Studio. A chart, summary, translation or table run reads *Evidence · Not scored*. A string of autosaves folds into one *Document saved N times* row that opens to the versions. After Approve & Save, the Receipts tab lands on the run that just happened, and the *Chart ready* banner closes with the review's decision.
- **How it benefits you.** The record reads the way you would say it, and the run you just approved is the one in front of you.
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

- **What shipped.** When a newer Flow is waiting, the title bar shows a teal **Update ready** button with a download icon, to the right of the version it will replace. The plan pill now states your plan and nothing else.
- **How it benefits you.** You can see that an update is waiting, and press it. Before, the words sat as plain text inside the plan pill with nothing to press.
- **How to use it.** Press **Update ready** to read what changed and install. Flow ▸ Check for Updates… checks right now, any time.

## Flow 1.5.1 · build 1404 · 27 August 2026

### The first update that arrived through Flow

- **What shipped.** The first Flow delivered by Flow itself: no download, and nothing to drag into Applications. Flow also writes the outcome of every update check to the system log, so if a check ever fails there is a reason to read instead of a guess.
- **How it benefits you.** Every update from here on arrives the same way. Press **Install Update** and Flow restarts on the new version with your documents, settings and receipts exactly where they were.
- **How to use it.** Flow looks for a new version at launch and then at most once every six hours. Settings ▸ Flow System says which version you are on and what the last check found; Flow ▸ Check for Updates… runs one by hand.

## Flow 1.5 · build 1382 · 26 August 2026 · the launch

Flow is a native Mac app for professional documents with AI agency built in. It works on ordinary folders of plain Markdown files: AI proposes each change, you approve it, and the record stays with the file. This is what the launch release brought.

### See the change before it becomes yours

- **What shipped.** Seven AI actions: Proofread, Summarize, Translate, two table conversions, Expand with Sources and Visualize. Each proposes an exact diff in **Review Changes**. You can approve it, reject it, or keep reviewing. Your document changes only when you say so, and a change that fails one of your guardrails stays on the record if you override it.
- **How it benefits you.** Nothing is written without your approval, and you read the writing first and the decision after.
- **How to use it.** Open the document in the Editor (⌥⌘/ switches between Reader and Editor), select text, and press an AI tool on the document toolbar or choose it from the Agency menu.

### Turn plain text into finished visuals

- **What shipped.** 34 chart types and 20 diagram types drawn in place, offline, from readable text that stays in your file. A chart editor with the chart chosen by type, a Chart gallery that opens any chart in its own tab, pictures rendered in place with an image editor for the alt text, and **Visualize**, which asks Flow to turn a table, list or paragraph into a chart you review before it lands.
- **How it benefits you.** The picture lives in the Markdown. Any other editor still reads the same file.
- **How to use it.** Format ▸ Insert Chart or Diagram…, or the toolbar's Insert Chart. [[Visualization Gallery]] shows every kind Flow draws. Select a table and press Visualize (⇧⌘V).

### Choose where every model may run

- **What shipped.** Four domains, each with its own switch: Local, LAN, Cloud prepaid, Cloud postpaid. Flow Runtime is built in, so there is nothing else to install; models already in Ollama or LM Studio are found without copying them; OpenAI, Anthropic and OpenRouter run on your own key; Codex CLI and Claude Code subscriptions can run Flow's actions too. Smart Routing lets your rules pick the model, and the screen names the rule that decided. Benchmarks measures your local models on this Mac, and a fallback that would cross a boundary stops and asks first, with the estimated cost on the *Leaves this Mac* sheet.
- **How it benefits you.** Your text leaves this Mac only if you allow it, and you know the cost before you approve.
- **How to use it.** Settings ▸ Models (⌘4 opens Settings) for the domains, providers and keys; Settings ▸ Benchmarks to measure; Settings ▸ Smart Routing for the rules. The **Ideas** panel (⌘3) proposes only the setup this Mac actually needs, and nothing runs until you say so.

### Keep the proof with the work

- **What shipped.** Every approved run leaves a receipt with the model, the route, the cost, the checks, the evidence, and the revision you chose to keep. Guardrails can be set once and adjusted per document. Version History shows every saved revision and lets you restore one.
- **How it benefits you.** The record stays with the file instead of disappearing with a chat session, and a difference between two versions says when it cannot be fairly compared.
- **How to use it.** A document's Receipts tab; ⇧⌘Y for Version History; Settings ▸ Guardrails for the rules.

### The document is the workplace

- **What shipped.** Folders of Markdown you already own, with no import step and no private format. Editor, Reader and Source views; search across every open folder, by words and by meaning; tabs, panes and split view; Recents; wiki links and backlinks; tables with a grid view; footnotes; dictation that stays on this Mac; and this Guide, opened side by side with Ideas on first launch. Reading, writing, searching, organising and exporting are free forever. Pro adds the AI, with 10 Pro Days included to start.
- **How it benefits you.** Other apps read the same files. Deleting a file sends it to the system Trash. If a subscription ends, the AI stops and the documents remain open and editable.
- **How to use it.** Add Folder in the sidebar; ⌘N for a new document; ⌘] to split; ⇧⌘F to search; ⇧⌘D to dictate.

### What the launch build fixed

Build 1382 replaced the day's first build, 1255, with the fixes the launch walk found: a new document opens in the Editor with a caret; a table or an Expand draft is written with a blank line either side so it renders in the review and in the saved file; a chart proposed on a document open in the Editor draws; Settings ▸ Flow System says *Flow is up to date* when there is nothing newer; Settings keeps equal margins in a split pane on a 14" MacBook Pro; the *Leaves this Mac* sheet says what its estimate prices; the editor toolbar carries Insert Image and Insert Chart; and choosing a picture lands you on the document that received it.
