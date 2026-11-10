
# How to Run a One-Person Company with AI Agents

If you already pay for Claude Code, Codex or Cursor, you can open five sessions at once. The hard part starts the next morning: none of them remembers what happened, two of them edited the same file, and you spend the first hour re-explaining the project.

The fix is not a smarter model. It is a folder that every session reads before it does anything. This guide shows the setup we use to run XyneX as a one-person company, step by step.

## The idea in one paragraph

**One folder is the company.** Files are the memory. A brief is a job description. A three-line status note replaces the stand-up meeting. Anything that leaves the folder — a post, an email, a price change, a payment — waits for the owner's yes.

## Step 1 — Create the folder and a workspace guide

Make a folder such as `my-studio/` and put a `CLAUDE.md` at the top. Claude Code reads this file automatically; Codex and many other agents read `AGENTS.md`, so add one that says "Read CLAUDE.md". In the guide, write:

- what the company does, in one sentence
- the languages you publish in
- tone rules (for example: plain words, no invented numbers)
- what agents must never do without asking

Keep it under one screen. Agents read it every session.

## Step 2 — Define five roles

You don't need more than five to start:

| Role | Job |
|---|---|
| Lead | Keeps the board and the checklist, splits work into briefs |
| Researcher | Finds facts, marks each one as verified (with link) or inference |
| Builder | Makes small, working files: scripts, templates, pages |
| Writer | Writes each language natively, using a glossary for fixed terms |
| Checker | Reopens every deliverable against its brief |

Start with lead + builder + checker. Add the others when you have the work.

## Step 3 — Rank ideas with two numbers

Put every idea in an inbox file. Score each on **difficulty** (1 = a weekend, 5 = needs a team or licences) and **profit band** (1–5). Divide profit by difficulty. Work on anything at 1.2 or above this week; park the rest. Before you start, write a seven-day test with a pass rule ("20 sales in 7 days") and a stop rule.

## Step 4 — One brief per session

A brief has four parts: the goal (checkable), the files to read, the folder to write in, and a done-when checklist. The checklist is what stops an agent from "improving" forever. Give each session its own build folder so two sessions never edit the same file.

## Step 5 — Status notes instead of meetings

After each meaningful step, each session updates `STATUS/<name>.md` with three things: done, open, and the exact next step. When a session runs out of context, the next one starts with: *"Read CLAUDE.md, your brief and your STATUS note. Continue from the next step."* It picks up in under a minute.

## Step 6 — Approval gates

List the actions that always wait for you: publishing, messaging real people, listing or pricing, spending, using keys or customer data, deleting others' files, accepting terms. Agents prepare a request with *what*, *files* and *how to undo*; you reply "yes #3". A yes for one item never carries over to the next. Keep keys out of files entirely — write only the variable names, keep values in your local environment.

## A 20-minute daily loop

Morning: read the lead's status, answer every open question, approve or decline queued actions one by one. Then tell each session "read your brief and status, continue". Evening: open one deliverable and try it yourself.

## Get the folder ready-made

The **One-Person AI Company Pack** is this setup as an empty folder: workspace guide, five roles, board, brief and status templates, six checklists, seven prompts and three filled examples, in English and Simplified Chinese. It's plain Markdown, CSV and JSON, so it works with Claude Code, Codex or Cursor. [See what's inside and the price (US$9.99/month)](https://xynex.sekai.center/pricing).

## FAQ

### Do I need to know how to code?
No. The pack is text files. You copy a folder, fill in blanks in `CLAUDE.md`, and paste prompts into your AI tool. Coding helps only if you want builder sessions to write scripts.

### Which AI tools does this work with?
Any agent that can read files in a folder. Claude Code reads `CLAUDE.md`; Codex and many others read `AGENTS.md`; in Cursor you add `CLAUDE.md` to the project rules.

### How many AI sessions should I run at once?
Start with three: lead, builder and checker. We keep at most three build sessions on "this week" items at a time, because the owner's daily review is the bottleneck.

### Will the agents post or spend money on their own?
Not with this setup. Publishing, messaging, pricing and spending are approval gates: the agent drafts, you act.

### What does the pack cost?
US$9.99 per month plus any tax shown at checkout, with new versions sent by email while you're subscribed. Details are on the [pricing page](https://xynex.sekai.center/pricing).

```json-ld
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {"@type": "Question", "name": "Do I need to know how to code?", "acceptedAnswer": {"@type": "Answer", "text": "No. The pack is text files. You copy a folder, fill in blanks in CLAUDE.md, and paste prompts into your AI tool. Coding helps only if you want builder sessions to write scripts."}},
    {"@type": "Question", "name": "Which AI tools does this work with?", "acceptedAnswer": {"@type": "Answer", "text": "Any agent that can read files in a folder. Claude Code reads CLAUDE.md; Codex and many others read AGENTS.md; in Cursor you add CLAUDE.md to the project rules."}},
    {"@type": "Question", "name": "How many AI sessions should I run at once?", "acceptedAnswer": {"@type": "Answer", "text": "Start with three: lead, builder and checker. We keep at most three build sessions on this-week items at a time, because the owner's daily review is the bottleneck."}},
    {"@type": "Question", "name": "Will the agents post or spend money on their own?", "acceptedAnswer": {"@type": "Answer", "text": "Not with this setup. Publishing, messaging, pricing and spending are approval gates: the agent drafts, you act."}},
    {"@type": "Question", "name": "What does the pack cost?", "acceptedAnswer": {"@type": "Answer", "text": "US$9.99 per month plus any tax shown at checkout, with new versions sent by email while you're subscribed. Details: https://xynex.sekai.center/pricing"}}
  ]
}
```
