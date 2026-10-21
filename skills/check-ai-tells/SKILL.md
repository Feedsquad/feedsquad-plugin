---
name: check-ai-tells
description: Use when the user asks whether a draft sounds machine-written, wants a post checked before it goes out, or pastes text to review for AI tells.
---

# Check a draft for AI tells

A tell is a signal of low-effort writing. It is never proof that a machine wrote the text.

1. Find out the target platform if it is not clear. `lint_post` accepts `linkedin`, `x` and `threads`.
2. Call `lint_post` with the text and the platform.
3. Read the verdict. Explain each hit in plain words using its evidence and rationale. Hits marked advisory are suggestions.
4. When a hit carries an `ai_tell_id`, call `get_ai_tell` with that id. Read its false-positive notes before you recommend a change.
5. If the user asks which patterns exist, call `list_ai_tells`.
6. Rewrite only the flagged parts and keep the user's voice. Do not add facts the user did not give you.
7. Call `lint_post` again on the rewrite. Show the before and the after.
8. If the text is a saved post, ask before you change it. Save the rewrite with `update_post` only after the user agrees.
