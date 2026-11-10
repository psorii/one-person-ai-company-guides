
# Chat Checkout: What Your Product Feed Needs Before an Assistant Can Sell

Buying is moving into the conversation. The assistant answers, the buyer says yes, the order happens inside the chat. Your catalog either participates or gets a polite "visit the site".

Six requirements decide it.

## 1. A stable product identifier
One ID per variant, never reused, never recycled after a SKU dies. Reusing IDs is the fastest way to have an assistant sell the wrong item.

## 2. Price and currency that match the page
Agents are strict here. A mismatch between feed and page is treated as unreliable, and the item is dropped rather than guessed.

## 3. Availability with a timestamp
"In stock" without a checked-at time is not usable. The assistant needs to know whether the number is fresh.

## 4. Shipping cost and window per destination
Chat checkout fails at the last step when shipping is unknown. Country-level cost and a delivery window are the minimum.

## 5. Return policy in structured form
Days, who pays, and where. A link to a PDF is not structured; a three-field policy is.

## 6. Tax behaviour per market
Included, added at checkout, or exempt — stated, not inferred.

## What to fix first

Order by revenue, then fix the six fields for the top 20 products. Most stores find that 60–80% of chat-visible queries touch those 20 items.

Then test like a buyer: ask the assistant for the product by a phrase a customer would use, and see whether it can answer price, stock and shipping without leaving the chat.

## Why this is not the same as SEO

SEO optimises for a click. Chat checkout optimises for a **decision** made inside the conversation. The click can be skipped; the fields cannot.

That also means the failure mode is quiet: no ranking drop, no error page — just an assistant that says "I can't confirm that" and a buyer who leaves.

## Where this becomes a service

The [$199 chat-checkout feed setup](https://xynex.sekai.center/services) maps your export against the six requirements, fixes the top 20 products, and re-tests by asking an assistant the five questions customers actually use. Three business days, no admin login.

Pair it with the [$99 catalog readiness audit](https://xynex.sekai.center/guides/catalog-readiness-ai-agents) if the underlying attributes are also thin.

## FAQ

### Do I need a special platform?
No. The six fields can live in a CSV or any feed format your platform exports.

### How often does the feed need refreshing?
At least daily for stock, and immediately after a price change.

### What does the setup cost?
$199 per catalog. See the [pricing page](https://xynex.sekai.center/pricing) for the template pack if you also run agents on the store.

```json-ld
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {"@type": "Question", "name": "Do I need a special platform?", "acceptedAnswer": {"@type": "Answer", "text": "No. The six fields can live in a CSV or any feed format your platform exports."}},
    {"@type": "Question", "name": "How often does the feed need refreshing?", "acceptedAnswer": {"@type": "Answer", "text": "At least daily for stock, and immediately after a price change."}},
    {"@type": "Question", "name": "What does the setup cost?", "acceptedAnswer": {"@type": "Answer", "text": "199 USD per catalog. Details: https://xynex.sekai.center/pricing"}}
  ]
}
```
