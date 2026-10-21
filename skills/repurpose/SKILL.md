---
name: repurpose
description: Use when the user wants one post, article or idea turned into versions for other social platforms with FeedSquad.
---

# Repurpose one piece for other platforms

1. Get the source text. The user may paste it. For a saved post, find it with `search_posts` and read it with `get_post`.
2. Call `list_accounts` to see which platforms are connected. Ask which platforms to target if it is not clear.
3. Call `adapt_for_platform` with the source as `draft` and the target `platforms`. Pass an `angle` when the user wants a different framing.
4. Call `lint_post` on each version and fix every block hit.
5. Show the versions side by side and revise them on the user's feedback.
6. Save each version the user keeps with `create_post`. Each one is saved as a draft.
7. Approve a version with `confirm_post` and `action: "approve"` only after the user says yes to it.
8. Never call `publish_post` unless the user asks for a post to go live right now.
