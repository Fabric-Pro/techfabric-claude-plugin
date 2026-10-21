---
name: "status"
description: "List your drafts and where each one stands, or one draft in detail: what's failing, its preview, and what to do next. Use only when the engineer runs this command."
argument-hint: "[draft id]"
disable-model-invocation: true
---

List my techfabric.com drafts and where each stands, through the techfabric MCP server.

If I typed a draft id with this command: Call get_status with the id. get_status may first ask me a question from the blog writer, which waits on a fact only I have: show it to me and let me answer it. Then tell me, briefly: its state and what that means, the preview link, what is failing and which of those I may publish past, and the one thing to do next.

Otherwise: Call list_drafts (if the server lacks it, read the resources it lists as techfabric://drafts/{id}): my drafts, newest first, each with its state, preview link and next_action. Filter it as I ask: state (checks_failing, ready_to_publish, open and the rest), kind, and created_after and created_before for a day ("yesterday" is the day before the `today` in its answer). If it is refused for a sign-in, tell me to connect with Microsoft (my client's Connect or Authenticate button for the techfabric server). Show me a short table: id, title, state, created, preview link, next step. For one in state checks_failing, call get_status with its id and add what is failing.

Never show or ask for the editor link: it is only in my email.

What I typed with the command: $ARGUMENTS
