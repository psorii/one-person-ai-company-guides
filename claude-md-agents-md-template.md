
# CLAUDE.md and AGENTS.md: a Template for a Multi-Agent Workspace

`CLAUDE.md` is the file Claude Code reads when it starts in a folder. `AGENTS.md` plays the same part for Codex and many other agents. When you run several sessions on one project, these two files decide whether every session starts on the same page or each one guesses.

Below is the structure we use, a skeleton you can copy, and the mistakes that cost us time.

## Keep one source of truth

Write everything in `CLAUDE.md`. Make `AGENTS.md` two lines long:

```text
# AGENTS.md
Read CLAUDE.md in this folder first and follow it. It is the single source of truth.
```

Two full copies drift apart within a week. One file plus a pointer doesn't.

## What goes in CLAUDE.md

| Section | What to write | Length |
|---|---|---|
| Company | Name, what you sell, who buys, in one or two sentences | 2 lines |
| Languages | Which languages you publish in, and "write each natively" | 1 line |
| Tone | Plain words; no invented numbers, reviews or "I tested" claims | 3–5 bullets |
| Working style | Read the board and your brief first; stay in your build folder; small checkable deliverables | 3–5 bullets |
| Approval gates | Actions that always wait for the owner's yes | link to the gate list |
| Keys | "Env var names only; never write values" | 1 line |
| Done means | Deliver the file, reopen it against the brief checklist, update STATUS | 2–3 bullets |
| Coordination | Where status notes go and when to write them | 1–2 lines |

Aim for one screen. Long guides get skimmed by agents as much as by people.

## A copyable skeleton

```text
# CLAUDE.md — {{COMPANY}}

{{COMPANY}} sells {{PRODUCT}} to {{BUYER}}. Owner: {{OWNER}}.

## Languages
{{EN, ZH}}. Write each language natively, not word for word. Fixed terms: memory/GLOSSARY.csv.

## Tone
- Plain, friendly words.
- No invented numbers, reviews or testimonials. Unsure → write "to confirm".

## Working style
- Read board/RANKED_BOARD.md and your brief in briefs/ before starting.
- Write only inside builds/<your-area>/.
- Prefer small, checkable deliverables: a file, a script, a draft.

## Ask first (see ops/APPROVAL_GATES.md)
Publishing, messaging real people, listing or pricing, spending, keys or customer data, deleting others' files, accepting terms.

## Keys
Env var names only (ops/env.example). Values live in the owner's local environment.

## Done means
Deliver the file → reopen it against your brief's checklist → update STATUS/<your-name>.md (done, open, next step).
```

## Five mistakes we made

1. **Long background stories.** Agents don't need the founding story; they need rules they can check.
2. **Rules without a place to write.** "Keep notes" fails; "write STATUS/<name>.md after each step" works.
3. **No "done means".** Without it, sessions keep polishing.
4. **Two full instruction files.** They drift. Use the pointer.
5. **Secrets as examples.** Even a sample key teaches the pattern. Show names only.

## Get the full folder

The template above is one file of the **One-Person AI Company Pack**, which also includes five role briefs, a ranked board, status and weekly-report templates, approval gates, six checklists and seven prompts in English and Chinese. [See what's inside (US$9.99/month)](https://xynex.sekai.center/pricing).

## FAQ

### What is the difference between CLAUDE.md and AGENTS.md?
They hold the same kind of instructions for different tools. Claude Code reads CLAUDE.md; Codex and many other agents read AGENTS.md. Keep the content in one and make the other point to it.

### Where do I put CLAUDE.md?
At the top of the folder you open the agent in. Sub-folders can have their own when one area needs extra rules.

### How long should CLAUDE.md be?
About one screen. Put long material — the board, glossary, gate list — in separate files and link to them.

### Can I use the same CLAUDE.md for several agents at once?
Yes. That's the point: every session reads the same rules, then its own brief and status note.

### Is the template in the pack in Chinese too?
Yes. The checklists, prompts and start guide are in English and Simplified Chinese. Details on the [pricing page](https://xynex.sekai.center/pricing).

```json-ld
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {"@type": "Question", "name": "What is the difference between CLAUDE.md and AGENTS.md?", "acceptedAnswer": {"@type": "Answer", "text": "They hold the same kind of instructions for different tools. Claude Code reads CLAUDE.md; Codex and many other agents read AGENTS.md. Keep the content in one and make the other point to it."}},
    {"@type": "Question", "name": "Where do I put CLAUDE.md?", "acceptedAnswer": {"@type": "Answer", "text": "At the top of the folder you open the agent in. Sub-folders can have their own when one area needs extra rules."}},
    {"@type": "Question", "name": "How long should CLAUDE.md be?", "acceptedAnswer": {"@type": "Answer", "text": "About one screen. Put long material such as the board, glossary and gate list in separate files and link to them."}},
    {"@type": "Question", "name": "Can I use the same CLAUDE.md for several agents at once?", "acceptedAnswer": {"@type": "Answer", "text": "Yes. Every session reads the same rules, then its own brief and status note."}},
    {"@type": "Question", "name": "Is the template in the pack in Chinese too?", "acceptedAnswer": {"@type": "Answer", "text": "Yes. The checklists, prompts and start guide are in English and Simplified Chinese. Details: https://xynex.sekai.center/pricing"}}
  ]
}
```
