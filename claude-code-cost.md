
# Why Your Claude Code Bill Climbs (Five Fixes That Cut Tokens)

The bill rarely climbs because you asked for more. It climbs because every task carries the same overhead, and the overhead grew without anyone noticing.

Five causes, each with a check you can run today.

## 1. The context file grew into a document

Every task loads `CLAUDE.md` again. At 700 words it is noise in the budget; at 4,000 it is the budget.

**Check:** `wc -w CLAUDE.md`
**Fix:** move history into `memory/`. Keep rules under 700 words. Reference long docs from the brief instead of the root file.

## 2. Sessions re-read the same files

An agent that opens the same 2,000-line file three times pays three times. A brief that says "read `src/`" invites exactly that.

**Check:** watch one session and count repeated reads of the same path.
**Fix:** name the files in the brief. "Read `src/api/routes.ts` lines 40-90" instead of "look at the API".

## 3. Sessions run for hours

Long sessions accumulate context that is no longer relevant: failed attempts, dead ends, reverted edits. You pay for all of it on every later turn.

**Check:** if a session has more than ~50 turns, it is probably carrying dead weight.
**Fix:** hand off. Write `done / open / next`, start a new session with that note and the brief. The status folder exists for this reason.

## 4. The wrong model for the job

Renaming files and drafting status notes do not need the most expensive model. Architecture decisions do.

**Check:** list the last ten tasks and what each actually required.
**Fix:** route by task type in the brief: cheap model for mechanical edits, expensive for design and debugging.

## 5. Nothing is cached or reused

Repeating the same explanation in every prompt is the most common leak. If a fact matters twice, it belongs in a file.

**Check:** search your prompts for the same paragraph appearing more than once.
**Fix:** move it into `memory/decisions.md` or the brief template.

## The number that tells you it worked

Tokens per shipped task.

```
tokens per task = total spend / tasks shipped
```

If it drops while shipped tasks stay flat, the fixes worked. If shipped tasks rise faster than spend, you are scaling correctly.

Measure for three weeks before changing anything else. One week is noise.

## What usually happens after the five fixes

- Context file cut to under 700 words: 15–30% fewer tokens per task.
- Named files instead of "read the repo": the largest single drop, often 2×.
- Handoff instead of hour-long sessions: fewer wasted turns at the end of the day.

None of it requires a new tool. It requires the file to be small and the brief to be specific.

Free check: [score your CLAUDE.md](https://xynex.sekai.center/check) — context budget is one of the twelve checks. If you want it rewritten instead, the [$29 context fix](https://xynex.sekai.center/org-skills) returns a corrected file in 24 hours.

## FAQ

### Does a smaller file really cost less?
Yes. The root file is loaded on every task, so its size multiplies by the number of tasks.

### Should I switch models to save money?
Only for mechanical work. On design and debugging, a cheaper model usually costs more in rework.

### What does the pack cost?
$9.99 per month at the founding price, or $79 per year. It moves to $19.99 on 2026-12-01. Details on the [pricing page](https://xynex.sekai.center/pricing).

```json-ld
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {"@type": "Question", "name": "Does a smaller file really cost less?", "acceptedAnswer": {"@type": "Answer", "text": "Yes. The root file is loaded on every task, so its size multiplies by the number of tasks."}},
    {"@type": "Question", "name": "Should I switch models to save money?", "acceptedAnswer": {"@type": "Answer", "text": "Only for mechanical work. On design and debugging, a cheaper model usually costs more in rework."}},
    {"@type": "Question", "name": "What does the pack cost?", "acceptedAnswer": {"@type": "Answer", "text": "9.99 USD per month at the founding price, or 79 USD per year. It moves to 19.99 USD on 2026-12-01. Details: https://xynex.sekai.center/pricing"}}
  ]
}
```
