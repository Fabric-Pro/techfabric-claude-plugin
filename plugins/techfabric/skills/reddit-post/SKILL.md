---
name: "reddit-post"
description: "Draft a Reddit post, or an answer to a thread, in your own voice, from a published techfabric.com post or your own notes: the real problem, what you tried, what worked, your numbers, the one-line disclosure, and the link only if it adds depth. Checked against the subreddit's rules and the site's writing rules. You post it yourself: nothing is posted, voted or commented for you. Use only when the engineer runs this command."
argument-hint: "<subreddit> [post URL or slug] [notes] [thread URL]"
disable-model-invocation: true
---

Draft a post for the subreddit I typed with this command (ask me if I typed none), in my voice, through the techfabric MCP server. I post it myself, by hand, from my own Reddit account.

1. **Read the rules.** Read the editorial_rules resource (techfabric://editorial/rules) first: client confidentiality and the client register decide what a Reddit post may say, as they do for an article. Name no client, and give no client's result, that our published article doesn't state.
2. **Get the kit.** Call reddit_post_kit with the subreddit I typed, and the post (its URL or slug), my notes and the thread URL I typed, whichever I gave. It returns the material, the subreddit's rules, the frame, the disclosure line, the link (if there is a post), the checklist and the steps to post it myself.
3. **Ask me what only I know.** Before you write, ask me for the problem I actually had, what I tried, what worked and the numbers I have, unless my notes already say. Wait for my answers. Never invent an experience, a number or a client. If the kit says the article is a colleague's (whose: colleague), its first-hand sentences are theirs: say so, never as mine.
4. **Draft.** Write it from the kit, as me, in the first person singular, in the kit's frame: a title that is a plain question or a plain finding, then the problem, what I tried, what worked and my numbers, with the whole substance in the post. Put the disclosure on its own line near the end: "I work at TechFabric, a Databricks partner." Add the kit's link only as the last line, and only if it adds depth the post can't hold. No marketing voice, no TechFabric pitch, no call to action, no hashtags, no emoji.
5. **Check it.** Call reddit_post_kit again with the same arguments and draft set to { title, body }. Rewrite each finding with level fix as its why says, keeping my facts, and call it again until lint.ready is true. Tell me about each finding with level warn: those are my call.
6. **Hand over.** Show me the title and body, the checklist and the post_it_yourself steps. If it is for r/dataengineering, tell me plainly to rewrite it in my own words before I post: that subreddit bans AI-generated or heavily AI-assisted text (rule 9). Don't post it, comment it, vote, schedule it or send it anywhere: I post it by hand.

The rules a Reddit post or answer is held to:

- Never automate Reddit: no agent or script posts, votes or comments, ever. You post from your own account, by hand.
- Disclose where you work in one line, every time: "I work at TechFabric, a Databricks partner."
- Contribute far more than you promote, about nine helpful answers and posts with no link of ours for every one that has a link.
- Put the whole substance in the post: the real problem, what you tried, what worked, the numbers you have. Someone who never clicks gets the full answer.
- The link to our article is optional, goes last, and only when it adds depth the post can't hold. Never a link-only post.
- Write in the first person singular, as yourself: what I ran into, what I tried. No marketing voice, no TechFabric pitch, no call to action, no hashtags, no emoji.
- The title is a plain question or a plain finding, the way an engineer would type it.
- Follow the subreddit's own rules, read on the day you post: flair, self-promotion limits, and in r/dataengineering, your own words only.
- Client confidentiality comes first, as in the editorial_rules resource: name no client and give no client's result that our published article doesn't state.
- Never ask colleagues to upvote or comment, and never post the same thing to several subreddits.

What I typed with the command: $ARGUMENTS
