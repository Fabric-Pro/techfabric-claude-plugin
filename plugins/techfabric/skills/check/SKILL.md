---
name: "check"
description: "Run techfabric.com's checks on a draft and explain each finding in plain words, with the fix your agent proposes. Nothing changes until you agree. Use only when the engineer runs this command."
argument-hint: "[draft id]"
disable-model-invocation: true
---

Check a techfabric.com draft against the site's checks, through the techfabric MCP server, and explain what they find.

1. **Read the rules.** Read the editorial_rules resource (techfabric://editorial/rules): each finding refers to one of them.
2. **Get the text.** If I typed a draft id with this command, call get_status with the id for draft.markdown, draft.base_sha, its kind and what is failing. Otherwise use the latest whole draft in this conversation, frontmatter included; if there isn't one, ask me for it.
3. **Check it.** Call lint_draft on the whole draft, and, if it is a case study, with kind "case-study" and its sources (ask me for them if you don't have them). It answers in about a second and costs nothing. Keep its findings and the judge_rubric it returns, and read the draft as the reader in that rubric, but don't change the text yet. Never use check_draft to iterate: it is the final verification, and it costs us. A finding that names a client I told you agreed to be named is the one exception: it clears when submit_draft (or update_draft) records client_confirmed, so leave the name in.
4. **Explain.** For each check that fails, tell me in plain words what it holds the draft to, quote the passage, and say how you'd fix it. Say which are wording and style checks I may publish past (Publish anyway, recorded under my name) and which have to pass: the page working (build, images, diagrams, links, placeholders), claims, our own spend and secrets.
5. **Fix with my agreement.** Propose the fixes and apply them only after I agree. For a filed draft, save them with update_draft (the id, the whole new text, draft.base_sha and, for a case study, the sources you linted with), and show me the preview link its answer starts with.
6. **Verify.** For a filed draft: call check_draft with the draft's id, once, on the saved text: the final verification by our judge and the blog writer's fact-check (five to ten minutes), and what publish_draft needs to have passed on exactly that text. Report the result.

Never show or ask for the editor link: it is only in my email.

What I typed with the command: $ARGUMENTS
