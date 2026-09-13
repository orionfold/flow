---
title: Research Brief
tags: ["customer-research", "example"]
jobs:
  - kind: gather
    definition: Research Refresh.md
    as: review
  - kind: keep-sources-fresh
    watch: ["Interview Register.md", "Visit Notes.md"]
  - kind: overnight-notes
---
# Research Brief

**Fictional discovery study · eleven interviews · one primary need per person**

## Approval records are the leading coded need, within a small biased sample

Five of eleven entries name an approval record as the primary need. All five sit in the enterprise group. This suggests a question for the next study; it does not estimate market prevalence.

```chart data: data/review-*.json#needs
chartType: Lollipop Chart
title: Five interviewees prioritised an approval record
subtitle: People · one code per person · n = 11
source: Fictional bundled example; replace with your own records
data:
  - {need: "Approval record", mentions: 5}
  - {need: "Faster review", mentions: 2}
  - {need: "Local access", mentions: 1}
  - {need: "Portable files", mentions: 3}
semantic_types:
  need: Category
  mentions: Count
encodings:
  y:
    field: need
  x:
    field: mentions
  color:
    field: need
    scheme: purples
```

## What to do with the finding

| Finding | Interpretation | Next question |
| --- | --- | --- |
| Approval record: 5 | Possible enterprise workflow need | What evidence must accompany an approval? |
| Portable files: 3 | Ownership matters to several solo users | Which export or handover failed last time? |
| Faster review: 2 | Time pressure is present | Where is review time actually spent? |
| Local access: 1 | One privacy or connectivity concern | Which data must remain local, and why? |

Read [[Interview Synthesis]], [[Visit Notes]] and [[Market Hypotheses]] for three different forms of research writing. They separate observation, interpretation and the next test.
## Make it yours

1. Copy this entire folder in Finder, give the copy a name, then choose **Add Folder** in Flow. Keep its local subfolders beside the documents.
2. Open **Interview Register** and choose **View ▸ Edit Table** to replace the fictional records. Keep the column names and edit the cells, then save. The saved definition controls the calculation; the living report’s Jobs control recurring work.
3. Add I12 with need “Portable files” and mentions 1. After Gather, that need should show **4** and the register should contain **12** interviews.
4. With this document open, choose **File ▸ Night Shift Jobs…** to review its saved work; save any changes and close the editor. Choose **Settings ▸ Night Shift ▸ Run now**, then inspect the changed table or chart and the Briefing. Gather uses local calculations; optional Overnight notes need a configured local model. Enable Night Shift only for scheduled runs.
5. Replace the illustrative prose with your own assessment after checking the inputs. A chart can refresh its numbers; it cannot certify the conclusions around it.


## Review notes

Keep your decision here. Optional Night Shift notes appear below after a configured local model runs.

<!-- night: notes -->
<!-- /night: notes -->
