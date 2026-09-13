---
title: Night Shift Handbook
tags: ["flow", "reference", "night-shift"]
---
# Night Shift Handbook

## Keep a useful document current

Night Shift runs the work a document declares, then records what changed. You choose the documents, sources and settings. Start with a copied workspace so its inputs and outputs belong to your work.

![A quiet desk prepared for the next morning](assets/quiet-desk.jpeg)

## Four jobs, plus the redraw

| Job | What it does | What to review |
| --- | --- | --- |
| Gather | Reads named files or web sources, calculates rows and saves a dated capture | The definition, source dates and output |
| Keep sources fresh | Compares named files, folders or public pages with the prior read | Changed source text and any failed reads |
| Reconcile against folder | Updates the named folder’s inventory | Added, removed or changed files |
| Overnight notes | Uses a configured local model to interpret the document’s numeric evidence | The notes and their limitations |
| Bound table or chart | Redraws from its named data without needing another job row | The new values and whether the narrative still holds |

Gather and redraw calculations do not need a model. Overnight notes do. The product checks numeric claims against its available rows; that check does not establish that every inference or source is correct. Review the result.

## Set up the work in the editors

1. On the main document, choose **File ▸ Night Shift Jobs…**. Choose the saved definition or sources it should use.
2. Open the linked definition document, then choose **File ▸ Edit Definition…** to inspect the sources, calculation steps and emitted rows.
3. Try one small input change, then choose **Settings ▸ Night Shift ▸ Run now**. A manual run works with scheduling off. Compare the result with the expected change in Make it yours.
4. Use the moon in the title bar or **Settings ▸ Night Shift** to configure the overnight window. Flow’s available controls show when the Mac can run and which model is ready.

**Run now works across your open folders.** For a first practice run, keep only the copied workspace open and review its saved jobs first. Reopen your other folders when you are ready to include their work.

## Source paths travel with the folder

A path such as `inputs/*.md#tables:Record` reads the matching local notes. A binding such as `data/review-*.json#summary` reads the newest matching capture by filename and the named row set. Keep the folder structure intact when you copy a workspace. A public web source makes a network request; a local definition does not connect to an external business system.

## The morning is reviewable

The Morning Briefing names changed documents and failed work. Open the document to inspect changes; Review Changes offers Keep or Revert, and History retains saved versions. An unchanged-input run should leave an unchanged document alone. A failed fetch is missing evidence, not a fresh value.

## Choose what is automatic

Numeric tables and charts can regenerate from their inputs. An authored diagram, conclusion, draft letter or recommendation may still need your review. Every workspace explains that distinction. Remove an optional web watch or Overnight notes job if you do not want it.

| To practise | Good starting workspace |
| --- | --- |
| Local arithmetic | Household Budget or Living Document Starter |
| Several people’s updates | Team Status |
| Public source freshness | Competitor Watch |
| Questions from evidence | Insurance Renewal or Legal Matter |

The Guide’s folders are examples, not automatic integrations. Copy the one closest to your task and replace its sample inputs.

## Tables are inputs; Jobs repeat the work

Edit business records with the named table’s **Open in the table editor** control. On the living report, **File ▸ Night Shift Jobs…** shows the recurring work. Its linked saved definition opens with **File ▸ Edit Definition…** for changes to the calculation. Document properties and these technical declarations still travel in frontmatter; ordinary record edits do not require YAML.

A definition can read `Quarterly Close.md#table:Quarters`: the single table below the exact **Quarters** heading. A dated pattern such as `inputs/health-operations-*.md#table:Weeks` reads the newest complete packet. `inputs/*.md#tables:Record` reads the **Record** table from every matching file, useful for one update per person or one document per form. Keep headings and column names when replacing sample values; change the definition if you rename them.
