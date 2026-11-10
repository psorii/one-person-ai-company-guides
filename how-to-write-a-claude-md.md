
# How to Write a CLAUDE.md (Template and Five Worked Examples)

A CLAUDE.md is the file Claude Code reads before every task. It is not documentation for humans; it is the closest thing you have to a management layer. Write it like one: short, imperative, checkable.

## The skeleton

```markdown
# {{COMPANY}} — workspace guide

You work inside {{COMPANY}}, run by {{OWNER}}.
Mission: {{MISSION}}. Languages: {{LANGUAGES}}. Money goal: {{MONEY_GOAL}}.

## Five rules
1. Done = a file, a check, a next step. Never a paragraph.
2. Never without {{OWNER}}: post, send a customer email, change a price, issue a refund, deploy.
3. When rules conflict: safety > money > speed, and say which one you followed.
4. Ask at most one question, and only when the answer changes what you build.
5. After every step write: done / open / next.

## Folder map
briefs/  STATUS/  memory/  reports/  ops/

## Never
- Keys, tokens, .env values in files. Variable names only.
- Inventing numbers, reviews, customers or revenue.

## Status format
done: <files + what changed>
open: <unfinished>
next: <one action or the blocker>
```

That is 80% of the value. Everything below is refinement.

## Example 1 — solo founder, one product

```markdown
# Studio — workspace guide
Mission: sell two digital packs. Money goal: $3,000 by 2026-12-01.
Never without me: publish, price change, refund, deploy.
Done = file + test pass + status note.
```

Three lines of rules beat three pages of philosophy.

## Example 2 — agency with client work

```markdown
# Agency — workspace guide
Each client has a folder under clients/<name>/ with its own brief.
Never touch another client's folder. Never email a client without the account lead.
Every deliverable goes to clients/<name>/deliverables/ and gets a status note.
```

The ownership rule prevents the most expensive mistake: work landing in the wrong client folder.

## Example 3 — content team

```markdown
# Content — workspace guide
Voice: plain, specific, no hype words.
Every post: one claim, one proof, one next step.
Never publish unverified numbers; cite the source file in the same folder.
Publishing waits for the editor's yes.
```

## Example 4 — a repo with tests

```markdown
# Service — workspace guide
Run `npm test` before saying anything is done. Paste the tail of the output.
Never edit migrations or CI config without an issue number.
If a test fails twice, stop and write what you tried.
```

## Example 5 — bilingual work

```markdown
# Bilingual — workspace guide
Write each language natively, never line by line.
Chinese output uses 简体中文 unless the brief says otherwise.
Both versions ship together; one version alone is not done.
```

## The five mistakes

1. **Rules buried in prose.** "We generally prefer…" is a story. Write an imperative.
2. **Contradictions.** Two rules that fight; state precedence.
3. **Stale paths.** A command that no longer exists makes the agent guess.
4. **No trigger.** "Be careful with keys" is a mood; tie it to a command.
5. **No consequence.** Say what to do when a rule cannot be followed: stop, report, do not work around.

## Length

Under 700 words. Every task pays for this file in tokens. If it needs more, move detail into `memory/` and name it in the brief.

## Test it

Ask the agent to restate the five rules, then give it a task that tempts a violation. If it does the forbidden thing, the rule was not specific enough — the model is fine.

Free check: paste your file into the [score tool](https://xynex.sekai.center/check) for 12 checks and the three things to fix first. The [pricing page](https://xynex.sekai.center/pricing) has the full pack if you would rather start from a working version.

## FAQ

### How long should a CLAUDE.md be?
Under 700 words. One screen is the target, two is the limit.

### Does Codex read CLAUDE.md?
Codex and most other agents read `AGENTS.md`. Keep one file as the authority and point the other at it.

### What does the pack cost?
$9.99 per month at the founding price, or $79 per year. It moves to $19.99 on 2026-12-01. Details on the [pricing page](https://xynex.sekai.center/pricing).

```json-ld
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {"@type": "Question", "name": "How long should a CLAUDE.md be?", "acceptedAnswer": {"@type": "Answer", "text": "Under 700 words. One screen is the target, two is the limit."}},
    {"@type": "Question", "name": "Does Codex read CLAUDE.md?", "acceptedAnswer": {"@type": "Answer", "text": "Codex and most other agents read AGENTS.md. Keep one file as the authority and point the other at it."}},
    {"@type": "Question", "name": "What does the pack cost?", "acceptedAnswer": {"@type": "Answer", "text": "9.99 USD per month at the founding price, or 79 USD per year. It moves to 19.99 USD on 2026-12-01. Details: https://xynex.sekai.center/pricing"}}
  ]
}
```
