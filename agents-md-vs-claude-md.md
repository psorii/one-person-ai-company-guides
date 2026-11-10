
# AGENTS.md vs CLAUDE.md — Which File Does Your Tool Read?

Two names, one job: telling an agent how to work in this folder before it touches anything.

- **CLAUDE.md** — read by Claude Code (and tools built on the same convention).
- **AGENTS.md** — the cross-tool convention read by Codex and a growing set of other agents.

If your team uses one tool, you only need one file. The moment a second tool appears, you have the drift problem: two files, two versions of the truth, and nobody notices until an agent follows the stale one.

## The two-line setup that avoids drift

Pick one authority, usually `CLAUDE.md` because it is the richer format, then make the other file a pointer:

```markdown
# AGENTS.md

This repository is one company workspace. `CLAUDE.md` is the authority.
Read it first, then the latest file in `STATUS/`, then your brief in `briefs/`.

After every real step, append: done / open / next.
```

That is the whole file. No duplicated rules, nothing to keep in sync. When you change a rule, you change it once.

## What belongs in the authority file

The same five things regardless of tool:

1. **Done definition** — a file, a check, a next step.
2. **Gates** — post, customer email, price, refund, deploy.
3. **Precedence** — safety > money > speed, and say which one won.
4. **Question policy** — one question, only when it changes the build.
5. **Status format** — three lines after every step.

Tool-specific detail goes at the bottom, in a small section: how to run tests, where the folder lives, what the linter command is.

## Tool notes that actually differ

| | CLAUDE.md | AGENTS.md |
|---|---|---|
| Who reads it | Claude Code | Codex and other AGENTS.md-aware agents |
| Typical location | repo root | repo root |
| Nested files | supported in some setups | supported in some setups |
| Best use | the authority file | a pointer, or the authority if you never use Claude Code |

Nested files are the subtle one: if your tool supports per-directory files, a nested file usually wins for that subtree. That is useful for monorepos and dangerous for rules you want everywhere — put global rules at the root.

## A test that takes two minutes

1. Change one rule in the authority file.
2. Ask each tool to restate the rules before starting a task.
3. If a tool still cites the old rule, it is reading a different file.

That is how drift gets caught before it ships something wrong.

## When you have three or more tools

Stop maintaining prose per tool. Keep the authority file, and generate the rest:

```sh
# one authority, generated pointers
cp CLAUDE.md AGENTS.md   # only if the tool tolerates the same content
```

Or keep a one-line pointer as above. Either way, one file is edited and reviewed.

Free check: paste your authority file into the [score tool](https://xynex.sekai.center/check) for 12 checks and the three fixes that matter most. If you want the full folder — roles, briefs, gates, checklists — see the [pricing page](https://xynex.sekai.center/pricing).

## FAQ

### Does Codex read CLAUDE.md?
Not by default. Codex reads `AGENTS.md`. Keep `CLAUDE.md` as the authority and make `AGENTS.md` a two-line pointer.

### Can I just copy CLAUDE.md to AGENTS.md?
Yes if you never edit one without the other. In practice that fails within a week; a pointer does not.

### What does the pack cost?
$9.99 per month at the founding price, or $79 per year. It moves to $19.99 on 2026-12-01. Details on the [pricing page](https://xynex.sekai.center/pricing).

```json-ld
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {"@type": "Question", "name": "Does Codex read CLAUDE.md?", "acceptedAnswer": {"@type": "Answer", "text": "Not by default. Codex reads AGENTS.md. Keep CLAUDE.md as the authority and make AGENTS.md a two-line pointer."}},
    {"@type": "Question", "name": "Can I just copy CLAUDE.md to AGENTS.md?", "acceptedAnswer": {"@type": "Answer", "text": "Yes if you never edit one without the other. In practice that fails within a week; a pointer does not."}},
    {"@type": "Question", "name": "What does the pack cost?", "acceptedAnswer": {"@type": "Answer", "text": "9.99 USD per month at the founding price, or 79 USD per year. It moves to 19.99 USD on 2026-12-01. Details: https://xynex.sekai.center/pricing"}}
  ]
}
```
