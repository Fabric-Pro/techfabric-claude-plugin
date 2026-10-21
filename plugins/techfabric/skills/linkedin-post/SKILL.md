---
name: "linkedin-post"
description: "Draft a LinkedIn post about a published techfabric.com post, in your voice, checked against the site's writing rules. You post it yourself: nothing is posted for you. Use only when the engineer runs this command."
argument-hint: "<post URL or slug>"
disable-model-invocation: true
---

Draft a LinkedIn post about the published techfabric.com post (the post's URL or slug I typed with this command; ask me if I typed none), in my voice, through the techfabric MCP server. I post it myself.

1. **Read the rules.** Read the editorial_rules resource (techfabric://editorial/rules) first: client confidentiality and the client register decide what the LinkedIn post may say, as they do for the article. Name no client, and give no client's result, that the article itself doesn't state.
2. **Get the kit.** Call social_post_kit with post set to it. It returns the post's key points and first-hand sentences, the link to use (with the LinkedIn campaign), my voice notes, the rules and LinkedIn's lengths. If it says the post is a colleague's, write as someone sharing their work, never claiming it as mine.
3. **Draft.** Write the LinkedIn post from the kit, in the first person, in my voice: open on the reader's problem in one concrete sentence that fits before "see more", say one thing the post found, and put the kit's link in it once, near the end. Use only facts the post or I give you.
4. **Check it.** Call lint_social with the text and the post. Rewrite each finding as its why says, keeping my facts, and call it again until ready is true.
5. **Hand over.** Show me the finished text, its length, and anything you couldn't confirm from the post or from me. Don't post it, schedule it or send it anywhere: I post it from my own LinkedIn.

The rules a LinkedIn post is held to:

- Write it in the engineer's own voice, in the first person, about work they did or saw: what broke, what we built, what we measured. Never claim experience the article doesn't back.
- About the first 210 characters show before "see more" (less on some phones): open with the reader's problem, in one concrete sentence, never with how you feel about posting.
- Aim for 1000 to 1300 characters; LinkedIn stops a post at 3000.
- Put the article's link from the kit in the post, once, near the end. Never 'link in the comments'.
- Short paragraphs of two or three sentences. Not a column of one-line paragraphs.
- At most 3 hashtags, at the end, and only ones people follow. No emoji, no engagement bait ('Agree?', 'Thoughts?').
- The site's writing rules apply: no em dashes, no listed AI words, no 'not X, it's Y', straight quotes. Every number comes from the article, or from the engineer when it is about our own work.
- Client confidentiality comes first, as in the editorial_rules resource: name no client and give no client's result that the article itself doesn't state. lint_social can't check this; you do.
- The engineer posts it themselves, from their own LinkedIn. Nothing here posts anything.

What I typed with the command: $ARGUMENTS
