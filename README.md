# TechFabric for Claude Code

> This repository is generated. Its source is TechFabric's website repository, Fabric-Pro/techfabric-web (`scripts/harness-pack.mjs`), which pushes every change here and tags each release. A commit made here directly is overwritten by the next release, so pull requests belong in Fabric-Pro/techfabric-web. Report problems as issues here.

TechFabric's engineers write, check, preview and publish blog posts and case studies for [techfabric.com](https://www.techfabric.com) from Claude Code, through the techfabric.com MCP server (https://www.techfabric.com/mcp). This plugin adds that server, a command for each step and the techfabric-blog skill. Anyone can use the server's read tools, which search and read techfabric.com's published pages without signing in.

## Install

From a shell:

```sh
claude plugin marketplace add Fabric-Pro/techfabric-claude-plugin
claude plugin install techfabric@techfabric
```

Or inside a Claude Code session, run `/plugin marketplace add Fabric-Pro/techfabric-claude-plugin`, then `/plugin install techfabric@techfabric`.

If git isn't installed, add it from techfabric.com instead. Both marketplaces are named techfabric, so add only one:

```sh
claude plugin marketplace add https://www.techfabric.com/mcp-servers/harness/claude-code/marketplace.json
claude plugin install techfabric@techfabric
```

## Sign in to write

Writing needs a techfabric.com account. Run `/mcp`, pick the techfabric server, choose Authenticate and sign in with your @techfabric.com Microsoft account.

## Commands

Type `/techfabric:` to see them. Everything after a command is passed to it, so `/techfabric:write-post how we cut Lakeflow cold starts` works as written.

| Command | What it does |
| --- | --- |
| `/techfabric:write-post [topic, or today's brief]` | Write and publish a techfabric.com blog post under your byline, from today's brief or a topic of your own. Your agent asks you for the first-hand detail, lints, files and verifies the draft until every check passes, then publishes it only once you say yes. |
| `/techfabric:write-case-study <project> [client]` | Write and publish a techfabric.com case study about a project you worked on. Your agent asks for the outcome numbers and their sources, and for the client's confirmation before naming a client the register doesn't approve. It verifies the draft and publishes only once you say yes. |
| `/techfabric:check [draft id]` | Run techfabric.com's checks on a draft and explain each finding in plain words, with the fix your agent proposes. Nothing changes until you agree. |
| `/techfabric:preview <draft id>` | Show a draft as techfabric.com will publish it: the preview link, or the draft app in a host that renders MCP Apps. |
| `/techfabric:publish <draft id>` | Publish one of your drafts to techfabric.com. Your agent checks it, tells you what still fails, and publishes only after you say yes. |
| `/techfabric:revise <draft id or post URL> [feedback]` | Apply a reviewer's feedback, or your own change, to one of your drafts or to a post that's already live, check it again and save it, keeping your first-hand facts as they are. |
| `/techfabric:status [draft id]` | List your drafts and where each one stands, or one draft in detail: what's failing, its preview, and what to do next. |
| `/techfabric:blog-post-template [topic]` | Start a techfabric.com blog post from the ready-made template: the shape the checks hold it to, what goes in each part, and a skeleton your agent fills in from your own work. |
| `/techfabric:case-study-template [project]` | Start a techfabric.com case study from the ready-made template: the four sections, the card's frontmatter, the client and number rules, and a skeleton your agent fills in from the project. |
| `/techfabric:linkedin-post <post URL or slug>` | Draft a LinkedIn post about a published techfabric.com post, in your voice, checked against the site's writing rules. You post it yourself: nothing is posted for you. |
| `/techfabric:performance [post URL or slug]` | How one of your published posts is doing in Google: clicks, impressions, CTR and position against the month before, the searches it shows for, whether it's indexed, and what to improve. Leave the post out for all of yours. |

Each command gives Claude the exact sequence of tools to call, and reads the house rules from the server's editorial_rules resource. The techfabric-blog skill carries the same rules for when you write without a command.

Nothing is published until you say yes. A hook asks you again before every `publish_draft`, even in auto mode, and another reminds Claude to lint a draft before it saves it.

## Updates

Each release is tagged `techfabric--v<version>`. To pick one up, run `claude plugin marketplace update techfabric` and then `claude plugin update techfabric@techfabric`, or turn on auto-update for the marketplace under Marketplaces in `/plugin`.

## More

Every MCP server we run, and how to add each one to other agents: https://www.techfabric.com/mcp-servers. Privacy: https://www.techfabric.com/mcp-servers#privacy.

## Licence

[Apache-2.0](LICENSE).
