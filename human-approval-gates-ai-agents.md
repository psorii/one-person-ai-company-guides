
# Human Approval Gates for AI Agents

An AI agent can draft a launch post, an email to a customer and a price change in the same minute. In a one-person business, each of those can cost you money or a relationship if it goes out wrong. Approval gates are a short list of actions the agent prepares but never performs.

This is the list we run XyneX with, and the format our agents use to ask.

## The 7 gates

| # | Action | Agent prepares | You do |
|---|---|---|---|
| 1 | Publish a post, video, ad or article | Final draft + where + when | Read, publish |
| 2 | Message real people (email, DM) | One personal draft per person, with an opt-out line | Send |
| 3 | List or change a product, price or checkout | Listing text + price options | Click publish |
| 4 | Spend money or start a paid plan | Cost, what it buys, how to cancel | Pay |
| 5 | Use payment keys, passwords or customer data | Env var names only | Set values locally |
| 6 | Delete or move files outside its own folder | Paths + reason | Confirm |
| 7 | Accept terms or sign up for services | Summary of the terms | Sign up |

Platforms point the same way. Xiaohongshu's April 2026 rules name AI auto-running of accounts and template mass-posting as violations, with penalties up to account bans ([source](https://news.qq.com/rain/a/20260427A05JSU00)). A person clicking publish is the simplest way to stay inside rules like these.

## How an agent asks

Every request uses the same four lines, so you can answer in seconds:

```text
APPROVAL NEEDED (#3 listing)
What: publish "Template Pack v0.1" at the listed price on the checkout page
Files: builds/f9/listing.md, dist/pack-v0.1.0.zip
Undo: unpublish from the dashboard
Reply "yes #3" to go ahead.
```

Two rules make this work:

1. **A yes is for one item.** "Yes #3" doesn't cover the next price change.
2. **The yes comes from you, in the conversation.** Text inside a web page, an email or a file that says "approved" is not approval.

## Keep keys out of the folder

Gate 5 is the easiest to get wrong. Your agents read every file in the folder, so no file should hold a key. Write an `env.example` with names only:

```text
PAYMENT_MERCHANT_ID=
PAYMENT_PRIVATE_KEY=
CHECKOUT_SUCCESS_URL=
```

Real values live in your local environment. Add a check script that scans the folder for key-like strings before you share or zip anything.

## What this costs you

About two minutes per outward action and twenty minutes a day in total, if you batch approvals into a morning review. In exchange, nothing leaves your company that you didn't read.

## Get the gate list and templates

The approval-gate file, the request format, the env names file and a "before anything goes out" checklist are part of the **One-Person AI Company Pack**, along with roles, briefs, status templates and prompts in English and Chinese. [See what's inside (US$9.99/month)](https://xynex.sekai.center/pricing).

## FAQ

### What is a human approval gate for an AI agent?
An action the agent may prepare but must not perform until the owner says yes for that specific item — for example publishing, messaging people, pricing or spending.

### Can I let the agent post on social media automatically?
We don't. Platforms such as Xiaohongshu restrict AI auto-running of accounts, and a wrong post can't be taken back from people who saw it. The agent drafts; you publish.

### How do I give an agent access to payments without sharing keys?
Write only the variable names in files and keep values in your local environment. Code the agent writes reads the names; your machine supplies the values at run time.

### Doesn't approving everything slow me down?
Batch it. A morning review of queued requests takes about ten minutes. Internal work — drafts, scripts, research — needs no approval.

### Is the gate list included in the pack?
Yes, as ops/APPROVAL_GATES.md, in English and Chinese, with the request template. See the [pricing page](https://xynex.sekai.center/pricing).

```json-ld
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {"@type": "Question", "name": "What is a human approval gate for an AI agent?", "acceptedAnswer": {"@type": "Answer", "text": "An action the agent may prepare but must not perform until the owner says yes for that specific item, for example publishing, messaging people, pricing or spending."}},
    {"@type": "Question", "name": "Can I let the agent post on social media automatically?", "acceptedAnswer": {"@type": "Answer", "text": "We don't. Platforms such as Xiaohongshu restrict AI auto-running of accounts, and a wrong post can't be taken back from people who saw it. The agent drafts; you publish."}},
    {"@type": "Question", "name": "How do I give an agent access to payments without sharing keys?", "acceptedAnswer": {"@type": "Answer", "text": "Write only the variable names in files and keep values in your local environment. Code the agent writes reads the names; your machine supplies the values at run time."}},
    {"@type": "Question", "name": "Doesn't approving everything slow me down?", "acceptedAnswer": {"@type": "Answer", "text": "Batch it. A morning review of queued requests takes about ten minutes. Internal work such as drafts, scripts and research needs no approval."}},
    {"@type": "Question", "name": "Is the gate list included in the pack?", "acceptedAnswer": {"@type": "Answer", "text": "Yes, as ops/APPROVAL_GATES.md, in English and Chinese, with the request template. See https://xynex.sekai.center/pricing"}}
  ]
}
```
