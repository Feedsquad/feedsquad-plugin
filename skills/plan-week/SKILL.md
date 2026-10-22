---
name: plan-week
description: Use when the user wants to plan the coming week of posts, asks what to post next, or wants the gaps in their FeedSquad calendar filled.
---

# Plan the week

1. Call `get_calendar` with `start_date` set to today and `end_date` set seven days ahead. The response gives the current time and the user's timezone, and each post's time on the user's clock, so you need no clock of your own. Note what is already scheduled or ready.
2. Call `get_calendar_health`. Read the gaps and the clusters it reports. If it reports many stale drafts, offer a backlog cleanup as a separate step.
3. Call `list_accounts` to see which platforms are connected.
4. If the user has published before, call `get_performance_insights` to see what worked. Use what it returns as a hint, not a rule.
5. Propose a short plan with one line per post. Each line names a day, a platform and one angle. Keep the count to what the user can sustain.
6. Ask for changes and adjust the plan until the user agrees with it.
7. Write a draft for each agreed line. Call `lint_post` on each draft and fix every block hit.
8. Call `create_posts` with `dry_run: true` to see the slot FeedSquad would propose for each draft. Show the drafts with those times.
9. When the user agrees, call `create_posts` again without the dry run. Each post is saved as a draft with a proposed time.
10. Approve a post with `confirm_post` and `action: "approve"` only after the user says yes to it. Approving a post with a proposed time schedules it.
11. If the user wants a different time, call `reschedule_post` before approval with exactly the time they name. A time without an offset, such as `2026-10-22T08:45`, is read on the user's clock. If they want another slot but name no time, call `find_next_slot` and quote its rationale.
