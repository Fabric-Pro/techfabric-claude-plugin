---
name: "continue-draft"
description: "Pick up one of your drafts where it stands: your agent reads where the draft stands and takes each next step through the checks, and publishes only once you say yes. Use only when the engineer runs this command."
argument-hint: "[draft id]"
disable-model-invocation: true
---

Continue my techfabric.com draft (the id I typed with this command; if I typed none, call list_drafts and ask me which) from where it stands, through the techfabric MCP server.

1. **Where it stands.** Call get_status with the id. get_status may first ask me a question from the blog writer, which waits on a fact only I have: show it to me and let me answer it. Tell me in one line its state and what is failing. If the server has preview_draft and your host renders MCP Apps, call preview_draft with the id once to open the draft app: it refreshes itself, so don't poll it.
2. **The next step.** Do what its next_action says: its call names the tool and the arguments it knows. Then do what the next answer's next_action says, and so on, one step at a time. Never guess a fact the checks ask for: ask me, and send my words as sources. When next_action says wait, say so, wait as its instruction says, then make the call it names; when it says report, stop and show me what's left.
3. **Publish, only with my yes.** When next_action says publish, show me the preview link and ask me: "Publish '<title>' to techfabric.com now?" and wait. Only on my yes, call publish_draft with the id: it asks me itself, or returns a one-time confirmation you send back only after I say yes. Then call get_status until its state is published and show me live_url.

If this is a scheduled or unattended run, or nobody answers you, never call publish_draft. Never ask me for the editor link in my email. If I want to edit in the browser, call open_editor and show me its link: it works once and expires 15 minutes after you ask for it.

What I typed with the command: $ARGUMENTS
