---
name: "publish"
description: "Publish one of your drafts to techfabric.com. Your agent checks it, tells you what still fails, and publishes only after you say yes. Use only when the engineer runs this command."
argument-hint: "<draft id>"
disable-model-invocation: true
---

Publish my techfabric.com draft (the id I typed with this command; ask me if I typed none), through the techfabric MCP server, only once I confirm.

1. **Where it stands.** Call get_status with the id. It has to be in state drafted. Tell me its title and show me its preview link.
2. **Verify.** If last_check didn't pass on the current text (on_current_text), call check_draft with the id, once: the final verification, five to ten minutes.
3. **If wording checks fail.** When only checks I may publish past fail, list each one by its id with its finding, and say they are wording and style checks I may publish past (Publish anyway), recorded under my name. Only if I say to publish anyway, send exactly those ids as override, on the first publish_draft call and again on the confirming one. If a check that has to pass fails (the page working, claims, our own spend, secrets), don't publish: say what to fix, and offer the revise command.
4. **Ask me.** Ask me: "Publish '<title>' to techfabric.com now?" and wait for yes.
5. **Publish.** Call publish_draft with the id (and override, if I chose Publish anyway). It asks me again itself, by a form in my client, or it returns a one-time confirmation: send that back as confirmation on a second call only after I said yes. (review_before_publishing returns the same question and confirmation without publishing anything.)
6. **After.** Call get_status until its state is published, then show me live_url. If the merge or deploy failed, it is back to drafted: tell me what failed.

Never publish without my yes in this conversation, and never in a scheduled or unattended run: if nobody can answer you, stop before publish_draft. Never send back a confirmation I didn't give. Never show or ask for the editor link: it is only in my email.

What I typed with the command: $ARGUMENTS
