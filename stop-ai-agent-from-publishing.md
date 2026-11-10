
# How to Stop an AI Agent From Publishing, Charging or Emailing Without You

An agent does not need to be malicious to cost you money. It needs one vague instruction and one action that leaves the folder.

Guardrails that work are boring: a list of actions, a sentence per action, a format for asking, a log, a review. Five parts, about 30 lines.

## 1. Name the actions, not the mood

"Be careful" is not a guardrail. This is:

```
Never do these without the owner's yes:
- publish a post or page
- send an email to anyone outside the team
- change a price, discount or plan
- issue a refund
- deploy to production
- delete data or rotate a key
```

Six lines. Each one is checkable, and each one maps to a real incident.

## 2. Gate the moment, not the topic

The rule has to trigger at the moment of action:

```
Before any command that posts, sends, charges, refunds or deploys:
stop. Write what you are about to do, to whom, and the exact text or amount.
Wait for "yes".
```

An agent that reads this will stop. An agent that reads "handle customer communication carefully" will not, because nothing in that sentence is a moment.

## 3. Give it a request format

Without a format, approvals arrive as paragraphs and get rubber-stamped.

```
APPROVAL REQUEST
action: <post | email | price | refund | deploy>
target: <where or to whom>
content: <the exact text, amount or diff>
risk if wrong: <one line>
```

Four lines. You can answer in one word.

## 4. Keep an approval log

Every gate that was passed gets one row:

```
date | action | target | decision | who
11-01 | post   | X      | yes      | owner
11-01 | price  | /pricing | no     | owner
```

This is how you notice the agent asking for the same risky thing every day, and how you prove what was approved when something goes wrong.

## 5. Review weekly, in five minutes

- Which gates were requested most? Those are the ambiguous ones.
- Which were approved every single time? Consider making them automatic, with a log.
- Which were never requested? Either the agent is not working, or the gate is too broad.

## What does not work

- **Long policy documents.** They get summarised away.
- **Trusting the model's judgement.** Judgement is exactly what you are gating.
- **Blocking everything.** An agent that cannot do anything produces nothing; you will disable the gates within a week.

The right shape is narrow: many actions allowed, six actions gated.

## Put it in the file it reads

All five parts belong in `CLAUDE.md` (and a pointer in `AGENTS.md`). If they live in a separate document, the agent will not read them on the task that matters.

The pack ships the seven-gate version with the request format and the log sheet. If you want to know whether your current file would hold, [score it free](https://xynex.sekai.center/check) — 12 checks, three fixes.

## FAQ

### Do I need a technical control, not a rule?
Rules cover judgement calls; technical controls cover hard limits. Use both: a rule for publishing, a spend limit on the account.

### What if the agent ignores the gate?
That means the rule is not in the file it reads at that moment. Put it at the top of `CLAUDE.md`, then test with a task that tempts a violation.

### What does the pack cost?
$9.99 per month at the founding price, or $79 per year. It moves to $19.99 on 2026-12-01. Details on the [pricing page](https://xynex.sekai.center/pricing).

```json-ld
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {"@type": "Question", "name": "Do I need a technical control, not a rule?", "acceptedAnswer": {"@type": "Answer", "text": "Rules cover judgement calls; technical controls cover hard limits. Use both: a rule for publishing, a spend limit on the account."}},
    {"@type": "Question", "name": "What if the agent ignores the gate?", "acceptedAnswer": {"@type": "Answer", "text": "That means the rule is not in the file it reads at that moment. Put it at the top of CLAUDE.md, then test with a task that tempts a violation."}},
    {"@type": "Question", "name": "What does the pack cost?", "acceptedAnswer": {"@type": "Answer", "text": "9.99 USD per month at the founding price, or 79 USD per year. It moves to 19.99 USD on 2026-12-01. Details: https://xynex.sekai.center/pricing"}}
  ]
}
```
