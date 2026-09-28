---
title: Newsletter Archive
category: business-teams
summary: "Write each issue by voice and by hand, keep every one as your own file, and collect them into a book."
tags: ["newsletter-archive", "example"]
jobs:
  - kind: gather
    definition: Issue Refresh.md
    as: review
  - kind: keep-sources-fresh
    watch: ["Issue Log.md", issues]
  - kind: reconcile-against-folder
    folder: issues
---
# Newsletter Archive

**Every issue, yours to keep.** Each issue is a Markdown file in `issues/`, so the archive outlives any platform. When enough have gone out, **Publish** collects them into an EPUB.

## Still a draft

<!-- data: data/review-*.json#drafts -->
| Issue | Date | Title | Words |
| --- | --- | --- | --- |
| I03 | 2026-09-12 | Writing in the open | 640 |

## The archive

<!-- data: data/review-*.json#issues -->
| Issue | Date | Title | Status |
| --- | --- | --- | --- |
| I01 | 2026-08-15 | What a quiet month teaches | Published |
| I02 | 2026-08-29 | Tools I stopped using | Published |
| I03 | 2026-09-12 | Writing in the open | Draft |

## Review notes

<!-- night: notes -->
<!-- /night: notes -->
