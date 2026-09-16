---
title: Job Search
category: personal-money
summary: "Applications, next actions and evidence-based tailoring."
tags: [job-search, dashboard, personal, night-shift]
jobs:
  - kind: gather
    definition: Job Search Refresh.md
    into: data
    as: search
  - kind: keep-sources-fresh
    watch: [Applications.md, resumes, https://www.apple.com/careers/us/, https://stripe.com/jobs/search, https://www.anthropic.com/careers]
  - kind: reconcile-against-folder
    folder: resumes
  - kind: overnight-notes
---
# Job Search

**Protect the next decision in your search: compare the offer deadline with the interviews still ahead.**

> Fictional product-designer search · as of 2 September 2026. Company names are real; applications, conversations and the offer are illustrative. Nothing here represents a real submission.

The example Notion decision is due 8 September, before the Stripe loop on 9 September. **Next action:** verify the offer's written expiry and decide whether to request more time. Compensation, written terms and the exact resume sent are missing; no offer ranking is justified yet.

[[Applications]] is the complete record. [[Job Search Refresh]] derives the active timeline; rejected or withdrawn applications stay in history. Keep posting captures, interview notes and resume versions beside this document so Search and source-based drafting can use the evidence you actually supplied.

## The pipeline

Active applications from the applied date to the recorded next step. Check the dates in the tracker when prioritizing follow-ups. An overdue row asks for a status check; it does not prove an obligation or that the next step occurred.

```chart data: data/search-*.json#active
chartType: Gantt Chart
title: Applications, from applied to the next step
subtitle: Coloured by stage
source: Applications.md via Job Search Refresh.md
data:
  - {id: "A2", company: "Apple", resume_version: "not recorded", role: "Product Designer", stage: "Phone screen", applied: "2026-08-19", next_step: "Hiring manager call", next_date: "2026-09-04", contact: "Referral from A. Lee", notes: "Ask about the team's design-system ownership"}
  - {id: "A5", company: "Linear", resume_version: "not recorded", role: "Product Designer", stage: "Take-home", applied: "2026-08-22", next_step: "Submit take-home", next_date: "2026-09-05", contact: "Recruiter via email", notes: "Three-day exercise; scope it to one flow"}
  - {id: "A6", company: "Notion", resume_version: "not recorded", role: "Senior Product Designer", stage: "Offer", applied: "2026-07-21", next_step: "Decide", next_date: "2026-09-08", contact: "Hiring manager", notes: "Offer in hand; compare against the Stripe loop"}
  - {id: "A1", company: "Stripe", resume_version: "not recorded", role: "Senior Product Designer", stage: "Onsite", applied: "2026-08-11", next_step: "Onsite loop", next_date: "2026-09-09", contact: "Recruiter via email", notes: "Portfolio review went well; loop is four sessions"}
  - {id: "A3", company: "Anthropic", resume_version: "not recorded", role: "Product Designer", stage: "Applied", applied: "2026-08-28", next_step: "Wait for response", next_date: "2026-09-11", contact: "", notes: "Applied through the careers page"}
semantic_types: {company: Name, applied: Date, next_date: Date, stage: Category}
encodings:
  y: {field: company}
  x: {field: applied}
  x2: {field: next_date}
  color: {field: stage, scheme: tableau10}
```

## The tracker

<!-- data: Applications.md#table:Applications -->
| Company | Role | Stage | Next step | Next date | Contact |
| --- | --- | --- | --- | --- | --- |
| Stripe | Senior Product Designer | Onsite | Onsite loop | 2026-09-09 | Recruiter via email |
| Apple | Product Designer | Phone screen | Hiring manager call | 2026-09-04 | Referral from A. Lee |
| Anthropic | Product Designer | Applied | Wait for response | 2026-09-11 |  |
| Figma | Staff Product Designer | Rejected |  | 2026-08-20 | Recruiter |
| Linear | Product Designer | Take-home | Submit take-home | 2026-09-05 | Recruiter via email |
| Notion | Senior Product Designer | Offer | Decide | 2026-09-08 | Hiring manager |

## Prep

<!-- data: Applications.md#table:Prep -->
| Item | Status |
| --- | --- |
| Portfolio site updated with the two 2026 case studies | done |
| Three references confirmed and warned | done |
| Take-home template ready (one flow, one page of rationale) | in progress |
| Compensation range decided before the Notion deadline | open |
| Questions for the Stripe loop written per session | open |

## Resume versions

The inventory records files, not submissions. Only an explicit application-to-version entry establishes which resume you sent. The supplied base is fictional; replace it before using any material externally.

```flow-folder resumes
| File | Size | Modified | Digest |
| --- | ---: | --- | --- |
| Resume — Base Version.md | 1885 |  |  |
```

Bundled file list; the inventory job fills timestamps and digests in your working copy.

## What changes on a run

The Gather filters and orders your authored tracker; bound views refresh from its capture. Resume inventory and source watches report changes. Public careers-page watches compare the pages you named; they do not provide personalized job matching. Optional local-model Overnight notes can identify recorded deadlines and missing information, but must not invent employer responses or offer terms.

## Make it yours

1. Copy the complete **Job Search** folder and add it in Flow. Keep `Applications`, the local definition, saved data and `resumes/` together.
2. Before the first run, review **File ▸ Night Shift Jobs…**. Remove the optional Apple, Stripe and Anthropic web watches for local-only work, or replace them with specific public pages you want compared.
3. Open [[Applications]], choose **View ▸ Edit Table**, change the example Linear stage to `Withdrawn`, and save. Review [[Job Search Refresh]] in the Definition editor, then run the saved job. The active timeline should shrink from five to four applications; the complete tracker must still contain six.
4. Replace all fictional applications and [[Resume — Base Version]]. Record a stable application ID, actual next date, posting evidence and exact sent-resume version. Keep unknown terms visibly unknown.
5. Choose **Settings ▸ Night Shift ▸ Run now**; enable Night Shift only for scheduled updates. Read the result and source changes. Drafting a tailored resume or message creates material to review; it does not submit or send it.

## Source and update map

| Part | Source | Update |
| --- | --- | --- |
| Active timeline | `data/search-*.json#active` | [[Job Search Refresh]] filters [[Applications]] |
| Complete tracker and preparation | [[Applications]] | Bound tables refresh from authored rows |
| Resume inventory | `resumes/` | Inventory job lists actual files |
| Career-page changes | Explicit public URLs in Jobs | Optional source-watch job |

## Overnight notes
<!-- night: notes -->
<!-- /night: notes -->
