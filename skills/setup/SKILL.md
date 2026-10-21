---
name: setup
description: Use when someone is new to FeedSquad, has just connected it, or asks how to get started. It checks which social accounts are connected and then writes a first post together with the user. It asks for nothing up front.
---

# Get started with FeedSquad

Ask for nothing before the first step. Learn about the user as you go.

1. Call `list_accounts`. Note which platforms show `connected: true`.
2. If no platform is connected, say so in one sentence. Ask which platform they post on most. Call `connect_platform` with that platform and share the link it returns. The user signs in on that page. Call `list_accounts` again when they say they are done.
3. If they would rather connect later, carry on. A draft does not need a connected account.
4. Ask one open question about what they want to post this week. A goal helps, but it is optional. If they have no answer, offer an idea based on what they have told you so far.
5. Write one short draft in their words. Do not invent numbers, customers or results.
6. Call `lint_post` with the draft and its platform. It accepts `linkedin`, `x` and `threads`. Fix every block hit before you show the draft.
7. Show the draft and ask what to change. Revise until the user is happy with it.
8. Save it with `create_post`. The post is saved as a draft. FeedSquad may propose a time for it, so quote that time and its rationale.
9. Ask whether to approve it. Call `confirm_post` with `action: "approve"` only after a clear yes. Approval with a proposed time schedules the post.
10. Never call `publish_post` unless the user asks to post right now.
11. Close with one next step the user can ask for, such as planning their week.
