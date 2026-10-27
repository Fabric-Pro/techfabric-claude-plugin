---
name: "revise-post"
description: "Change one of your published posts, or one of your drafts: apply a reviewer's feedback or your own change, to one section or the whole text, check it again and save it, keeping your first-hand facts as they are. A live post changes only when you publish the revision. Use only when the engineer runs this command."
argument-hint: "<post URL or slug, or draft id> [section] [feedback]"
disable-model-invocation: true
---

Revise my techfabric.com post or draft (the post URL, slug or draft id I typed with this command, then the section and the reviewer's feedback, if I typed them), through the techfabric MCP server.

1. **Read the rules.** Read the editorial_rules resource (techfabric://editorial/rules).
2. **A published post?** If the server has revise_post: if what I gave is a live post's URL or slug rather than an 8-character draft id, call revise_post with it first. Only its author or the blog's editor can. Use the revision id it returns as the id below, and show me the preview link its answer starts with. A revision keeps the post's URL, byline and publish date, so never change author: or the slug; a title change keeps the URL.
3. **Get the draft.** Call get_status with the id for draft.markdown, draft.base_hash, its kind and what is failing. get_status may first ask me a question from the blog writer, which waits on a fact only I have: show it to me and let me answer it.
4. **The section and the feedback.** If what I typed after the post or id starts with one of its headings, that is the section; the rest is the feedback. If there is no feedback, ask me what the reviewer asked for, and wait.
5. **Revise.** Apply the feedback to the section I named, if any, and anywhere else the feedback needs; otherwise the whole text. Keep my first-hand facts, numbers and quotes as they are; if the feedback needs a fact only I have, ask me for it rather than writing around it.
6. **Check it.** Call lint_draft on the whole draft, with the draft's id and the whole text as markdown (it lints the text as that draft: its kind, slug, images and sources). It answers in about a second and costs nothing. Do what its next_action says: rewrite each passage in rewrite_plan as its fix says, keeping every fact I gave you, and call it again, until ready is true. Don't stop early. Then read the draft as the reader in its judge_rubric, answer each question as that reader would, and revise until every answer clears its threshold. Never use check_draft to iterate: it is the final verification, and it costs us. A finding that names a client I told you agreed to be named is the one exception: it clears when submit_draft (or update_draft) records client_confirmed, so leave the name in.
7. **Save.** Call update_draft with the id, the whole new text and draft.base_hash (for a case study, new sources and client_confirmed only as I told you). If it is refused because the draft changed, call get_status again and redo the edit on the new text. Show me the preview link its answer starts with.
8. **Hand over.** Tell me what you changed and why, and what you didn't. A revision of a live post goes live only when I publish it, with the publish command, after I say yes. Never ask me for the editor link in my email. If I want to edit in the browser, call open_editor and show me its link: it works once and expires 15 minutes after you ask for it.

What I typed with the command: $ARGUMENTS
