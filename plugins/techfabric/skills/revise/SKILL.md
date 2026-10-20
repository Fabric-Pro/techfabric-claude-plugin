---
name: "revise"
description: "Apply a reviewer's feedback to one of your drafts, check it again and save it, keeping your first-hand facts as they are. Use only when the engineer runs this command."
argument-hint: "<draft id> [feedback]"
disable-model-invocation: true
---

Revise my techfabric.com draft (the id I typed with this command, and the reviewer's feedback after it), through the techfabric MCP server.

1. **Read the rules.** Read the editorial_rules resource (techfabric://editorial/rules).
2. **Get the draft.** Call get_status with the id for draft.markdown, draft.base_sha, its kind and what is failing. get_status may first ask me a question from the blog's drafting agent, which waits on a fact only I have: show it to me and let me answer it.
3. **The feedback.** Take it from what I typed after the id. If there is none, ask me what the reviewer asked for, and wait.
4. **Revise.** Apply the feedback to the whole text. Keep my first-hand facts, numbers and quotes as they are; if the feedback needs a fact only I have, ask me for it rather than writing around it.
5. **Check it.** Call lint_draft on the whole draft, with the draft's kind from get_status and, for a case study, its sources (ask me for them if you don't have them). It answers in about a second and costs nothing. Fix each finding in the passage it names and call it again, until ready is true. Then read the draft as the reader in its judge_rubric, answer each question as that reader would, and revise until every answer clears its threshold. Never use check_draft to iterate: it is the final verification, and it costs us. A finding that names a client I told you agreed to be named is the one exception: it clears when submit_draft (or update_draft) records client_confirmed, so leave the name in.
6. **Save.** Call update_draft with the id, the whole new text and draft.base_sha (the same kind, and for a case study its sources and client_confirmed only as I told you). If it is refused because the draft changed, call get_status again and redo the edit on the new text. Show me the preview link its answer starts with.
7. **Hand over.** Tell me what you changed and why, and what you didn't. Never show or ask for the editor link: it is only in my email.

What I typed with the command: $ARGUMENTS
