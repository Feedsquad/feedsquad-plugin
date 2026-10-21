---
name: clear-backlog
description: Use when old drafts pile up in FeedSquad, the calendar feels cluttered, or the user asks to clean out stale drafts.
---

# Clear the draft backlog

1. Call `get_calendar_health`. Read how many stale drafts it reports.
2. If there are no stale drafts, say so and stop.
3. Call `archive_posts` with `criteria: { "status": "draft" }` and `dry_run: true`. Nothing changes during a dry run.
4. Show the user the `would_archive` count and a few drafts from the sample.
5. Explain that archiving is not deleting. Archived drafts stay in the FeedSquad dashboard under Archived, where they can be restored.
6. Ask whether to archive them. Repeat the same call with `dry_run: false` only after a clear yes.
7. Report how many drafts were archived.
8. Never use `delete_post` to clear a backlog. Archiving can be undone and deleting cannot.
