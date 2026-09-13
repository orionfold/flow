---
title: Job Search Refresh
tags: [job-search, definition]
sources:
  applications: Applications.md#table:Applications
emit:
  active:
    from: applications
    steps:
      - {filter: "stage != 'Rejected' && stage != 'Withdrawn'"}
      - {sort: next_date}
---
# The next-action view

[[Applications]] remains the complete history. This definition selects active applications and sorts their recorded next dates for [[Job Search]]. It does not infer that an interview happened, submit an application, discover matching jobs, or send a follow-up.

With this definition open, choose **File ▸ Edit Definition…** to inspect the filter and preview its rows. A closed application remains in the source tracker and is removed only from this active view.

The definition and its saved capture stay in this folder when you copy it. The complete application source is never rewritten by this filter. After a run, check the result and capture date before relying on a deadline; this definition orders recorded dates but cannot verify that they are still agreed with an employer.

| Part | Rule |
| --- | --- |
| Input | Applications.md, the complete application history |
| Filter | Exclude Rejected and Withdrawn from the active view |
| Order | Recorded next date, earliest first |
| Result | A dated search capture; source history is preserved |
