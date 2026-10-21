---
name: "status"
description: "List your drafts and where each one stands, or one draft in detail: what's failing, its preview, and what to do next. Use only when the engineer runs this command."
argument-hint: "[draft id]"
disable-model-invocation: true
---

List my techfabric.com drafts and where each stands, through the techfabric MCP server.

If I typed a draft id with this command: Call get_status with the id. get_status may first ask me a question from the blog writer, which waits on a fact only I have: show it to me and let me answer it. Then tell me, briefly: its state and what that means, the preview link, what is failing and which of those I may publish past, and the one thing to do next.

Otherwise: My drafts are the resources the server lists as techfabric://drafts/{id}, newest first: read the list if your host can, and call get_status for each one in state drafted (waiting on me). If you can't list them, ask me for the ids. Show me a short table: id, title, state, preview link, what is failing.

Never show or ask for the editor link: it is only in my email.

What I typed with the command: $ARGUMENTS
