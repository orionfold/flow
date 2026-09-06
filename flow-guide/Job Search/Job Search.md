---
title: Job Search
tags: [job-search, dashboard, personal, night-shift]
jobs:
  - kind: keep-sources-fresh
    watch: [Applications.md, resumes, https://www.apple.com/careers/us/, https://stripe.com/jobs/search, https://www.anthropic.com/careers]
  - kind: reconcile-against-folder
    folder: resumes
  - kind: overnight-notes
---
# Job Search

Every application, where it stands, and what happens next, on a timeline you
can read at a glance. Nothing on this page needs a script: the tracker and
the timeline are drawn from the front matter of [[Applications]] each night,
the careers pages you list above are watched for changes, and the resume
versions in `resumes/` are inventoried so the version you sent is on record.

## The pipeline

Read from [[Applications]]. A bar that ends in the past is a follow-up you
owe.

```chart data: Applications.md#applications
chartType: Gantt Chart
title: Applications, from applied to the next step
subtitle: Coloured by stage
source: Applications.md, front matter
data:
  - {company: "Stripe", role: "Senior Product Designer", stage: "Onsite", applied: "2026-08-11", next_step: "Onsite loop", next_date: "2026-09-09", contact: "Recruiter via email", notes: "Portfolio review went well; loop is four sessions"}
  - {company: "Apple", role: "Product Designer", stage: "Phone screen", applied: "2026-08-19", next_step: "Hiring manager call", next_date: "2026-09-04", contact: "Referral from A. Lee", notes: "Ask about the team's design-system ownership"}
  - {company: "Anthropic", role: "Product Designer", stage: "Applied", applied: "2026-08-28", next_step: "Wait for response", next_date: "2026-09-11", contact: "", notes: "Applied through the careers page"}
  - {company: "Figma", role: "Staff Product Designer", stage: "Rejected", applied: "2026-07-30", next_step: "", next_date: "2026-08-20", contact: "Recruiter", notes: "Level mismatch; try again at senior"}
  - {company: "Linear", role: "Product Designer", stage: "Take-home", applied: "2026-08-22", next_step: "Submit take-home", next_date: "2026-09-05", contact: "Recruiter via email", notes: "Three-day exercise; scope it to one flow"}
  - {company: "Notion", role: "Senior Product Designer", stage: "Offer", applied: "2026-07-21", next_step: "Decide", next_date: "2026-09-08", contact: "Hiring manager", notes: "Offer in hand; compare against the Stripe loop"}
semantic_types: {company: Name, applied: Date, next_date: Date, stage: Category}
encodings:
  y: {field: company}
  x: {field: applied}
  x2: {field: next_date}
  color: {field: stage}
```

## The tracker

<!-- data: Applications.md#applications -->
| Company | Role | Stage | Next step | Next date | Contact |
| --- | --- | --- | --- | --- | --- |
| Stripe | Senior Product Designer | Onsite | Onsite loop | 2026-09-09 | Recruiter via email |
| Apple | Product Designer | Phone screen | Hiring manager call | 2026-09-04 | Referral from A. Lee |
| Anthropic | Product Designer | Applied | Wait for response | 2026-09-11 |  |
| Figma | Staff Product Designer | Rejected |  | 2026-08-20 | Recruiter |
| Linear | Product Designer | Take-home | Submit take-home | 2026-09-05 | Recruiter via email |
| Notion | Senior Product Designer | Offer | Decide | 2026-09-08 | Hiring manager |

## Prep

<!-- data: Applications.md#prep -->
| Item | Status |
| --- | --- |
| Portfolio site updated with the two 2026 case studies | done |
| Three references confirmed and warned | done |
| Take-home template ready (one flow, one page of rationale) | in progress |
| Compensation range decided before the Notion deadline | open |
| Questions for the Stripe loop written per session | open |

## Resume versions

The Night Shift keeps this list current: one file per tailored version,
named for the company it went to.

```flow-folder resumes
| File | Size | Modified | Digest |
| --- | ---: | --- | --- |
| Resume — Base Version.md | 920 | 2026-09-03T04:43:34Z | f28669eba612 |
```

## What you will see in the morning

- **A careers page changed.** One of the pages you watch gained or lost a
  posting; the Briefing shows the text that changed. Add any company's
  careers page to `watch` above, and it is watched from the next night.
- **You moved an application.** You edited a stage after a call; the tracker
  and the timeline show it, and the Briefing shows the diff.
- **A tailored resume landed.** The inventory names the new file.

## Make it yours

1. Edit the front matter of [[Applications]]: your applications and your
   prep list.
2. Put the careers pages you care about in `watch` at the top of this page.
   Only public `https` pages; each nightly fetch leaves a receipt.
3. Keep tailored resumes in `resumes/`, one file per company.
4. Turn the Night Shift on: the moon in the title bar, or Settings ▸ Night
   Shift.

## How this page is built

| Block | Construct | Bound to | Redrawn by |
| --- | --- | --- | --- |
| The pipeline | Gantt Chart | `Applications.md#applications` | the night alone |
| The tracker, Prep | tables | `Applications.md#applications`, `#prep` | the night alone |
| Resume versions | `flow-folder` inventory | `resumes/` | the night alone |
| Careers pages | `watch` in the `jobs:` block | three public pages | the night alone |

The same list draws the chart and the table: a Gantt reads `applied` and
`next_date` as its two ends and `stage` as its colour, and the table's header
names the columns it wants, in the order it wants them and in its own words —
*Next step* over `next_step`.

## Overnight notes
<!-- night: notes -->
<!-- /night: notes -->
