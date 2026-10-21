---
name: write-campaign
description: Use when the user wants a campaign, a launch series or a sequence of posts around one theme in FeedSquad.
---

# Write a campaign

1. Ask for the theme and the goal in one question. If the user has no answer, look at recent posts with `search_posts` and suggest a theme.
2. Call `list_accounts` to confirm the platform is connected. Pass a `company_page_id` only when the user wants to post as a company page.
3. Write every post yourself, because `create_campaign` does not write copy. Give each post one idea. Do not invent numbers, customers or results.
4. Call `lint_post` on each post and fix every block hit.
5. Show the whole sequence and revise it on the user's feedback.
6. Call `find_next_slot` for the platform to pick times that respect daily caps and spacing.
7. Call `get_calendar_health` before approval. Mention any cluster or gap it reports for the campaign window.
8. Call `create_campaign` with a name, the platform and the posts with their `schedule_for` times.
9. Ask whether to approve the campaign. Call `confirm_campaign` with `action: "approve_all"` only after a clear yes.
10. `approve_all` never approves X posts. Show each X post on its own, in an X campaign or a mixed one. Call `confirm_post` with `action: "approve"` only after the user says yes to that post.
11. If the user wants to change one post first, edit it with `update_post` before approval.
12. Never call `publish_post` unless the user asks for a post to go live right now.
