---
name: "write-post"
description: "Draft a techfabric.com blog post under your byline, from today's brief or a topic of your own. Your agent asks you for the first-hand detail, checks the draft and files it; you publish it. Use only when the engineer runs this command."
argument-hint: "[topic, or today's brief]"
disable-model-invocation: true
---

Write a blog post for techfabric.com under my byline, through the techfabric MCP server.

1. **Read the rules.** Read the editorial_rules resource (techfabric://editorial/rules) before you write a word, and follow it over anything here. It is the only copy of the house rules, client confidentiality first. The rules the checks hold a post to most often: the reader is a technology or business leader deciding whether this matters to their organisation (the leadership reader), unless the topic names another; the opening pattern, where sentence one is the reader's problem in their words with a concrete detail and sentence two is who we are and our first-hand angle; a title that is one clause naming the subject; a description of 70 to 160 characters in the same order as the opening; a diagram (a mermaid block); and FAQs at the end.
2. **The topic.** Take it from what I typed with this command. If that is "today's brief", call get_brief. If its status is none, tell me its reason and stop: no topic of your own. Otherwise write on its topic and angle, for its target_query, from its sources and linking its internal_links where a reader would want them, and keep its brief_id for submit_draft. If it is a topic of my own, call the server's search tool (search) on the topic to see what techfabric.com already says, so the post adds to it rather than repeating it, and note the pages worth linking. If I typed nothing, ask me what the post is about, or whether to take today's brief, and wait.
3. **Ask for the first-hand part.** Look through this repository and my notes for real work on the topic, read only: change nothing. Then ask me, in one message, for what only I know: what we built or what broke, a number we measured and where it comes from, and what we'd do differently. Wait for my answers. Where I have none, write in TechFabric's "we'd" voice and claim no experience. Never invent a number, a result, a client or a quote.
4. **Draft.** Write the whole post: YAML frontmatter (title and description at least), an introduction before the first heading, the body, a diagram and the FAQs.
5. **Check it.** Call lint_draft on the whole draft. It answers in about a second and costs nothing. Fix each finding in the passage it names and call it again, until ready is true. Then read the draft as the reader in its judge_rubric, answer each question as that reader would, and revise until every answer clears its threshold. Never use check_draft to iterate: it is the final verification, and it costs us.
6. **Submit.** Call submit_draft with the title and the whole post, and the brief's brief_id if it is from the brief. Its answer starts with the preview link: show it to me.
7. **Hand over.** Finish with the preview link, what you assumed, and your questions for me. Don't publish: when I'm happy with it, the publish command verifies it and publishes it after asking me, or I publish from the editor link in my email. Never show or ask for the editor link: it is only in my email.

What I typed with the command: $ARGUMENTS
