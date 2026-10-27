---
name: "performance"
description: "How one of your published posts is doing in Google: clicks, impressions, CTR and position against the month before, the searches it shows for, whether it's indexed, and what to improve. Leave the post out for all of yours. Use only when the engineer runs this command."
argument-hint: "[post URL or slug]"
disable-model-invocation: true
---

Show me how the techfabric.com post I typed with this command is doing in Google, through the techfabric MCP server.

1. **Read the numbers.** Call post_performance with the post I typed, or with no post for all of mine. It reads Search Console: clicks, impressions, CTR and average position for the last 28 days against the 28 before, counting searches from the US only. In a host that renders MCP Apps it opens as a card.
2. **Explain.** Tell me, briefly and with the numbers: how it is doing against the month before, whether Google has indexed it, the searches it shows for, and each item in improve in plain words. For all of my posts, show the table and offer one post's detail.
3. **Act only with my yes.** For each item, say what you'd change, and change nothing until I agree. Read the editorial_rules resource (techfabric://editorial/rules) before you propose new wording. A live post changes through revise_post, then the same loop as a draft: lint_draft with the id and the edit, update_draft, check_draft with the id, and publish_draft only after I say yes.

Every figure comes from post_performance: never estimate one. If it says Search Console isn't connected, say so and stop. Never ask me for the editor link in my email. If I want to edit in the browser, call open_editor and show me its link: it works once and expires 15 minutes after you ask for it.

What I typed with the command: $ARGUMENTS
