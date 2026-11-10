
# Why Agents Ignore Your CLAUDE.md (and Five Fixes)

You wrote the rules. The agent read them. It still did the thing you forbade.

Nothing is broken. Context files fail for five boring reasons, and every one of them is a two-line edit.

## 1. The rule is buried in a story

Agents follow rules that look like rules. "We've found over time that it's usually better to ask before posting" is a story with a moral. It competes with 200 other sentences.

**Fix:** one imperative per line, at the top level.

```
Bad:  We generally prefer that anything customer-facing is reviewed first.
Good: Never post, email a customer, or change a price without the owner's yes.
```

## 2. Two rules disagree and nobody wins

"Keep responses short." Later: "Explain every change in detail before editing." The agent picks whichever it read last, or averages them into something useless.

**Fix:** state precedence explicitly.

```
If two rules conflict: safety > money > speed. Say which rule you are following.
```

## 3. The file describes a repo that no longer exists

It names `scripts/deploy.sh`, which was deleted in March. It says prices are $49. The agent tries, fails quietly, and falls back to guessing.

**Fix:** every path and number in the file must be checkable in one command. Add a line:

```
Before using any command in this file, confirm it exists: ls or --help. If it does not, stop and report.
```

## 4. The rule has no trigger

"Be careful with keys" is a mood. An agent cannot act on a mood at the moment it matters.

**Fix:** tie the rule to a moment.

```
Bad:  Be careful with secrets.
Good: Before any command that prints environment variables, keys or .env, stop and ask.
```

## 5. There is no consequence

A rule with no follow-up is a suggestion. Agents — like people — drift when nothing happens.

**Fix:** define the report, not the punishment.

```
If you cannot follow a rule, stop and write: rule, why, what you need. Do not proceed and do not work around it.
```

## The five-line core

If your file is long, make sure these five are unmistakable at the top:

```
1. Done = a file, a check, a next step. Never a paragraph.
2. Never touch keys, deploys, prices, refunds or customer email without the owner.
3. When rules conflict: safety > money > speed, and say which one you followed.
4. One question maximum, and only when the answer changes what you build.
5. Status after every step: done / open / next.
```

Everything else in the file is detail. Detail is useful only if the core is obeyed.

## Test it in ten minutes

1. Ask the agent to restate the five rules in its own words before starting.
2. Give it a task that tempts a violation (a "quick" price change).
3. Check whether it stops and asks, or just does it.
4. If it does it, the rule is not specific enough — not the model.

A context file is not documentation. It is the closest thing you have to a management layer. Write it like one.

---

*The pack ships a working `CLAUDE.md` + `AGENTS.md`, seven approval gates and a scoring board, in English and Chinese.*

## FAQ

### How long should CLAUDE.md be?
One screen for the rules, everything else on demand. A long file costs tokens on every task and dilutes every rule.

### Does the same apply to AGENTS.md?
Yes. Keep the five core rules identical in both files so no tool gets a weaker version.

### What does the pack cost?
US$9.99/month at the founding price. See the [pricing page](https://xynex.sekai.center/pricing).

```json-ld
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {"@type": "Question", "name": "How long should CLAUDE.md be?", "acceptedAnswer": {"@type": "Answer", "text": "One screen for the rules, everything else on demand. A long file costs tokens on every task and dilutes every rule."}},
    {"@type": "Question", "name": "Does the same apply to AGENTS.md?", "acceptedAnswer": {"@type": "Answer", "text": "Yes. Keep the five core rules identical in both files so no tool gets a weaker version."}},
    {"@type": "Question", "name": "What does the pack cost?", "acceptedAnswer": {"@type": "Answer", "text": "US$9.99 per month at the founding price. Details: https://xynex.sekai.center/pricing"}}
  ]
}
```
