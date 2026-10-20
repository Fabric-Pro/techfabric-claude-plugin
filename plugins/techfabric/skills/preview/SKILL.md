---
name: "preview"
description: "Show a draft as techfabric.com will publish it: the preview link, or the draft app in a host that renders MCP Apps. Use only when the engineer runs this command."
argument-hint: "<draft id>"
disable-model-invocation: true
---

Show me my techfabric.com draft (the id I typed with this command; ask me if I typed none) as it will be published, through the techfabric MCP server.

If the server has preview_draft: Call preview_draft with the id. In a host that renders MCP Apps, the draft opens in the conversation as techfabric.com will show it, with its checks beside it. Its text starts with the preview link either way: show me that link. Otherwise: Call get_status with the id and show me draft.preview_url. If it is null, the preview is still being built: say so and ask again in a few minutes.

Then say in one line what state it is in and whether anything is still failing. Never show or ask for the editor link: it is only in my email.

What I typed with the command: $ARGUMENTS
