
# Running Multiple Claude Code Sessions Without Chaos

Two sessions is a productivity trick. Five is a company — or a mess, depending on one decision you make before you open the second window.

The decision: **does every session read the same folder, or does each one invent its own context?**

## What goes wrong with parallel sessions

- Two sessions edit the same file and the second overwrites the first.
- Session three asks you to re-explain the project because it has no memory of session one.
- You cannot tell which session is ahead, so you spend the evening reading chat logs.
- One session decides to "helpfully" change the price on a page you were still drafting.

None of these are model problems. They are coordination problems, and they have file-shaped answers.

## The structure that scales to five

```
company/
├─ CLAUDE.md        # rules every session reads first (same file, no copies)
├─ AGENTS.md        # the same rules for non-Claude tools
├─ briefs/          # one file per job: B01.md, B02.md …
├─ STATUS/          # one file per job: the stand-up
├─ memory/          # decisions, glossary, prices — the things that must not drift
└─ ops/             # checklists and gates
```

Four properties make this work:

1. **One rules file.** Not one per repo, not one per session. If you need a variant, it is a brief, not a second `CLAUDE.md`.
2. **One brief per session.** A session with two jobs will do neither well, and you will not know which one it dropped.
3. **One status file per job.** Latest note wins. You read status, never chat.
4. **Ownership by file.** Each brief names the paths that session may touch. Collisions become visible before they happen.

## The handoff that saves the most time

When you start session B on work session A began, do not paste the chat. Paste three lines:

```
done: <files>
open: <unfinished>
next: <one action>
```

That is the entire handoff format, and it is why the status folder exists. A session that can read the previous status can continue; a session that needs the chat cannot.

## Keep context small on purpose

Every session loads `CLAUDE.md` on every task. A 4,000-line rules file costs tokens on every message and makes the agent worse at following any single rule.

Rules that keep it small:

- `CLAUDE.md` holds rules, not history. History goes to `memory/decisions.md`.
- Long references (API docs, brand voice) load on demand, named in the brief.
- Delete dead paths. A rule about a tool you removed is pure cost.
- One screen is a good target for the rules file. Two is the limit.

## What to gate when several sessions run at once

With one session, mistakes are slow. With five, they are parallel. Gate the actions that leave the folder:

- publish, send, charge, refund, change a price, deploy.

Each gate is a line in `CLAUDE.md`: "never without the owner's yes", plus the checklist in `ops/`. Nothing elaborate is needed; what matters is that all five sessions read the same gate.

## A first day that does not collapse

1. Write `CLAUDE.md` with five rules and the three-line status format.
2. Create three briefs, not five. Lead, builder, checker.
3. Give each brief an owned path.
4. Run one day. Read only status files.
5. Only then add the fourth and fifth role.

Most people add sessions faster than they add structure, then conclude that agents do not work. The structure is the product; the sessions are just workers.

---

*The full folder — 5 roles, 6 checklists, 7 prompts, 3 filled examples, 7 approval gates, English and Chinese — is $9.99/month at the founding price.*

## FAQ

### How many sessions should I run?
Start with three: lead, builder, checker. Add a fourth only when the status notes stay readable for a week.

### How do I stop two sessions editing the same file?
Give every brief an owned path. A session that needs another path asks first.

### What does the pack cost?
US$9.99/month at the founding price. See the [pricing page](https://xynex.sekai.center/pricing).

```json-ld
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {"@type": "Question", "name": "How many sessions should I run?", "acceptedAnswer": {"@type": "Answer", "text": "Start with three: lead, builder, checker. Add a fourth only when the status notes stay readable for a week."}},
    {"@type": "Question", "name": "How do I stop two sessions editing the same file?", "acceptedAnswer": {"@type": "Answer", "text": "Give every brief an owned path. A session that needs another path asks first."}},
    {"@type": "Question", "name": "What does the pack cost?", "acceptedAnswer": {"@type": "Answer", "text": "US$9.99 per month at the founding price. Details: https://xynex.sekai.center/pricing"}}
  ]
}
```
