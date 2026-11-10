
# Three Numbers That Tell You If Your AI Agents Are Working

Most people judge an agent by how the conversation felt. That is why they cannot tell whether last week was good or just busy.

Three numbers fix it. One sheet, one row per week, five minutes.

## 1. Tasks shipped

Count finished work, not sessions started. A task counts when it produced a file someone else could use: a page, a script, a post, a report.

If you run five sessions and ship two tasks, you do not have five workers. You have two workers and three conversations.

## 2. Rework rate

The share of shipped tasks that had to be redone because the work was wrong, not because the brief changed.

```
rework rate = tasks redone / tasks shipped
```

Below 20% is healthy for agent work. Above 40% means the briefs are vague, not that the model is weak. The usual culprits: no definition of done, no owned path, no check.

## 3. Tokens per task

Total spend divided by tasks shipped. This is your unit cost.

It rises when the context file grows, when sessions re-read the same long document, or when an agent loops. If tokens per task doubles while shipped tasks stay flat, something is leaking — usually a 4,000-word rules file loaded on every call.

## The sheet

```
week | tasks shipped | rework rate | tokens/task | notes
W1   | 6             | 33%         | 41k         | briefs missing for B03, B04
W2   | 9             | 22%         | 38k         | added done-checks
W3   | 11            | 18%         | 35k         | split the checker role
```

Five columns. No dashboard, no tool. The value is the weekly read, not the chart.

## What to do with the numbers

- **Shipped flat, tokens up** → the context file is too big. Cut it.
- **Rework above 40%** → briefs lack a definition of done. Fix the template, not the model.
- **Shipped low, rework low** → the bottleneck is you, not the agent. Fewer sessions, one decision per day.
- **All three good for three weeks** → add a role, not a tool.

## Why not more metrics

Every extra column is a column nobody fills in on a bad week. Three numbers survive a busy Friday; a fourteen-metric dashboard does not.

If you want a starting sheet, the pack ships one with the weekly report template. If you want to know whether the underlying rules are any good first, [score your CLAUDE.md free](https://xynex.sekai.center/check) — 12 checks, no signup.

## FAQ

### How long before the numbers mean something?
Three weeks. One week is noise; two is a hint; three is a trend.

### What counts as a task?
Anything that produced a file another person could use without asking you what it means.

### What does the pack cost?
$9.99 per month at the founding price, or $79 per year. It moves to $19.99 on 2026-12-01. Details on the [pricing page](https://xynex.sekai.center/pricing).

```json-ld
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {"@type": "Question", "name": "How long before the numbers mean something?", "acceptedAnswer": {"@type": "Answer", "text": "Three weeks. One week is noise; two is a hint; three is a trend."}},
    {"@type": "Question", "name": "What counts as a task?", "acceptedAnswer": {"@type": "Answer", "text": "Anything that produced a file another person could use without asking you what it means."}},
    {"@type": "Question", "name": "What does the pack cost?", "acceptedAnswer": {"@type": "Answer", "text": "9.99 USD per month at the founding price, or 79 USD per year. It moves to 19.99 USD on 2026-12-01. Details: https://xynex.sekai.center/pricing"}}
  ]
}
```
