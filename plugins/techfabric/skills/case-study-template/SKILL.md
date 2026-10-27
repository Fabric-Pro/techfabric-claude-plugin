---
name: "case-study-template"
description: "Start a techfabric.com case study from the ready-made template: the four sections, the card's frontmatter, the client and number rules, and a skeleton your agent fills in from the project. Use only when the engineer runs this command."
argument-hint: "[project]"
disable-model-invocation: true
---

Start a techfabric.com case study under my byline from the ready-made template, through the techfabric MCP server, with kind "case-study".

1. **Read the rules.** Read the editorial_rules resource (techfabric://editorial/rules) before you write a word, and follow it over anything here. It is the only copy of the house rules, client confidentiality first. The rules the checks hold a case study to most often: the four sections in order (Challenge, Strategy, Solution, Results), each opening with a bold one-line statement; a description of 70 to 160 characters; every number backed by the sources you send; and no client named unless the register approves it or the engineer says the client agreed.
2. **The template.** It is below, and it is the techfabric://templates/case-study resource too. Follow its four sections and its two rules, and fill every {{fill: ...}} with my own material: lint_draft fails one left in.
3. **The project.** Take it from what I typed with this command. Ask me for what's missing: what was built, and for what kind of client. Wait for my answer.
4. **The client and the numbers.** Read the client register in the rules and tell me what it says about the client. Ask me for each outcome number and where it comes from, and send what I give you as sources. Send client_confirmed: true only if I tell you the client agreed to be named.
5. **Ask for the first-hand part.** Look through this repository and my notes for real work on the project, read only: change nothing. Then ask me, in one message, for what only I know: what we built or what broke, a number we measured and where it comes from, and what we'd do differently. Wait for my answers, and keep them word for word: send them as sources with submit_draft and update_draft, because the fact-check treats them as my own account of the work, and a first-hand sentence my sources don't back comes back as a finding. Where I have none, claim no experience: say plainly that we haven't run it, keep "we'd" for the recommendations that need it, and ask me what we did (a post that is mostly "we'd" fails speculative-voice). Say plainly what I built, in the past tense, with "we" as the actor ("we built a prototype that ..."), never our product or company in the third person; a prototype is called one once, in that sentence, and the post never disclaims itself (no caveat about the examples, the article or the diagram). Never invent a number, a result, a client or a quote.
6. **Check it.** Call lint_draft on the whole draft, with kind "case-study" and the sources. It answers in about a second and costs nothing. Do what its next_action says: rewrite each passage in rewrite_plan as its fix says, keeping every fact I gave you, and call it again, until ready is true. Don't stop early. Then read the draft as the reader in its judge_rubric, answer each question as that reader would, and revise until every answer clears its threshold. Never use check_draft to iterate: it is the final verification, and it costs us. When it passes, or next_action says submit, go straight on to Submit: don't stop after lint, because nothing is on the site until it is filed. A finding that names a client I told you agreed to be named is the one exception: it clears when submit_draft (or update_draft) records client_confirmed, so leave the name in.
7. **Submit, straight after lint.** File it now with submit_draft (it's private until you publish); the preview opens in the draft app. Call it with kind "case-study", the title, the whole case study and the sources. Show me the preview link its answer starts with.
8. **Verify.** Call check_draft with the id submit_draft returned. It waits while the draft is filed, then runs the final verification (the judge, the slop classifier and the fact-check), which starts on its own once the draft is filed (a couple of minutes) and takes about a minute: call it again while its next_action says wait. If it fails, do what next_action says: rewrite each passage in rewrite_plan, lint_draft with the id and the new text until it passes, save with update_draft, and check_draft again. When next_action says report (after six rounds), stop and show me what's left. Never guess a fact the fact-check asks for: ask me, and send my words as sources. To fix a fact finding, use its correction, cut the sentence back to what its source says, or remove it; never reword it into a new claim, because a rewrite that adds a number, a name or a result comes back as a new finding.
9. **Publish, only with my yes.** When check_draft passes, show me the preview link and what you assumed, then ask me: "Publish '<title>' to techfabric.com now?" and wait. Only on my yes, call publish_draft with the id: it asks me itself, or returns a one-time confirmation you send back only after I say yes. If I say no, or want changes, stop there: it stays a draft (the publish command finishes it later). After publishing, call get_status until its state is published and show me live_url. Never ask me for the editor link in my email. If I want to edit in the browser, call open_editor and show me its link: it works once and expires 15 minutes after you ask for it.

If this is a scheduled or unattended run, or nobody answers you, stop after submit_draft: give the preview link, what you assumed and your questions, and never call publish_draft.

# A techfabric.com case study: the template

The shape the site's checks hold a case study to, what goes in each part, and a skeleton to fill in. Submit the case study with kind "case-study". Read the editorial_rules resource (techfabric://editorial/rules) first: client confidentiality comes before everything here.

## Frontmatter

- title: what the client achieved, in one line, leading with their outcome rather than our work.
- description: one or two sentences for a stranger, 70 to 160 characters: the card's summary and the search snippet.
- sector: the client's industry, in a word or two.
- stack: a list of the platforms and tools the work used.
- track: one of ai, migration, other.
- client: only under the client rule below. Leave it out to anonymise the client.
- Never set logo, website, metrics, gallery, related: each is added by hand under an approval.

## Challenge

- ## Challenge comes first, and opens with a bold one-line statement of its argument, then prose.
- The situation the client was in, and why it mattered to them: a before state, never a failing of theirs.

## Strategy

- ## Strategy comes after ## Challenge, and opens with a bold one-line statement of its argument, then prose.
- The approach we chose, and why. Name an alternative we turned down only when the engineer says it was considered.

## Solution

- ## Solution comes after ## Strategy, and opens with a bold one-line statement of its argument, then prose.
- What we built: the architecture and the platforms.

## Results

- ## Results comes after ## Solution, and opens with a bold one-line statement of its argument, then prose.
- What changed, measured. Every number comes from the sources you send. With none, say what changed in words.

## The client rule

- Name the client only when the client register (the editorial_rules resource, signed in) approves naming them in a case study, or when the engineer says the client agreed: then send client_confirmed: true, which records their word under their name.
- Otherwise anonymise them by industry and size, in words with no figure ('a regional lender'), and name them nowhere: not in the title, the text, an image or a file name.

## Never write a client down

- Describe the before state as the client's situation, never as a failing of theirs: no word that scores a point off the people who hired us (editorial/voice.md).

## The number rule

- Every number in the case study must appear in the sources sent with it: the engineer's notes and the project's own records. One that isn't there is a finding.
- Ask the engineer for the outcome numbers and where each comes from. Never estimate one. A source isn't an approval: a client's metric is published only with an approval in the register.

## The skeleton

Replace every {{fill: ...}} with the engineer's own material. lint_draft fails one left in. Never fill one with a guess: ask the engineer.

````markdown
---
title: "{{fill: what the client achieved, in one line}}"
description: "{{fill: one or two sentences for a stranger, 70 to 160 characters}}"
sector: "{{fill: the client's industry}}"
stack:
  - "{{fill: a platform the work used}}"
track: "{{fill: one of ai, migration, other}}"
---

## Challenge

**{{fill: the challenge in one bold line}}**

{{fill: the challenge, in two paragraphs or more.}}

## Strategy

**{{fill: the strategy in one bold line}}**

{{fill: the strategy, in two paragraphs or more.}}

## Solution

**{{fill: the solution in one bold line}}**

{{fill: the solution, in two paragraphs or more.}}

## Results

**{{fill: the results in one bold line}}**

{{fill: what changed, with every number from the sources you send.}}

````


What I typed with the command: $ARGUMENTS
