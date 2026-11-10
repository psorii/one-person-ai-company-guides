
# Your Shopify AI Answers Are Stuck in English

You translated the storefront. The product pages are in German. Then a customer writes in German and the support answer comes back in English.

Nothing is broken. The translation covered the theme, not the answer layer. Five places hold the text that answers customers, and most stores localize two of them.

## Where the answers actually come from

1. **Product description and metafields** — translated if you translated products.
2. **FAQ / help content** — usually an app, usually English-only.
3. **Inbox saved replies / macros** — almost always English-only.
4. **Order and shipping notification templates** — often English-only.
5. **AI assistant / chat answers** — built from 1–4, so it inherits every gap.

The assistant is not the bug. It is a mirror.

## The five-step audit

**Step 1 — Export what customers see.** Open the storefront in each locale and screenshot: product page, FAQ, chat widget greeting, order confirmation email, shipping notification.

**Step 2 — Ask five real questions in the local language.** Not "hello" — the five questions your support answers weekly. Record which answers come back in the wrong language.

**Step 3 — Map each wrong answer to a source.** Product metafield, FAQ app entry, macro, notification template. Name the field, not the symptom.

**Step 4 — Fix in order of volume.** Notification templates and macros first: they repeat on every order. FAQ second. Product copy third.

**Step 5 — Re-test with the same five questions.** If two still fail, the source is a field you have not found yet — usually a second FAQ app or a theme string.

## What "translated" has to mean

- Same facts, not the same sentence structure.
- Local units, currency format, date format.
- Local legal wording for withdrawal and guarantee, where the market requires it.
- Product names that customers actually search for in that language.

Machine translation passes step 1 and fails step 3 almost every time.

## The cost of skipping it

A customer who writes in German and receives English does not complain. They leave. You see a lower conversion rate and blame the traffic.

## Where this becomes a service

The [$149 Shopify locale audit](https://xynex.sekai.center/services) runs these five steps on a development store copy and returns a CSV: field, current language, locale gap, exact replacement text, in English or Chinese. Five business days, no admin login — a product/theme export is enough.

If you also sell into the EU, pair it with the [$59 checkout check](https://xynex.sekai.center/guides/eu-checkout-rules): the checkout is the last place a wrong-language message costs you the order.

## FAQ

### Is this the same as translating the theme?
No. The theme is the frame; the answer layer is the text customers read when something goes wrong.

### Can the AI assistant translate on the fly?
It can, but it inherits the source language of the fields it reads. Fix the fields and the answers follow.

### What does the audit cost?
$149 per store, five business days. The template pack, if you run agents on the store, is $9.99/month at the founding price. See the [pricing page](https://xynex.sekai.center/pricing).

```json-ld
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {"@type": "Question", "name": "Is this the same as translating the theme?", "acceptedAnswer": {"@type": "Answer", "text": "No. The theme is the frame; the answer layer is the text customers read when something goes wrong."}},
    {"@type": "Question", "name": "Can the AI assistant translate on the fly?", "acceptedAnswer": {"@type": "Answer", "text": "It can, but it inherits the source language of the fields it reads. Fix the fields and the answers follow."}},
    {"@type": "Question", "name": "What does the audit cost?", "acceptedAnswer": {"@type": "Answer", "text": "149 USD per store, five business days. The template pack is 9.99 USD per month at the founding price. Details: https://xynex.sekai.center/pricing"}}
  ]
}
```
