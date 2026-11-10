
# Is Your Catalog Ready for AI Shopping Agents? A 10-Point Check

A shopping agent does not read your product page the way a person does. It reads structured attributes, matches them against the question, and answers. Empty fields become "does not fit", "not available", or silence.

Ten fields decide most of it. All ten are checkable in an afternoon.

## The ten fields

1. **Title that names the thing, not the campaign.** "Linen shirt, long sleeve, relaxed fit" beats "Summer Drop 03".
2. **Size and dimensions with units.** Agents do not infer "M" from a photo.
3. **Material composition.** Percentages, not "premium blend".
4. **Colour, with the actual name used in your swatches.**
5. **Compatibility** for anything that attaches to something else: model numbers, socket types, versions.
6. **Power or capacity** where relevant: watts, mAh, litres, load.
7. **What is in the box.** Agents answer "does it include the cable" constantly.
8. **Care or usage constraints.** Wash, temperature, indoor only, age range.
9. **Country availability and shipping windows.**
10. **Price, currency, and tax treatment per market.**

## Why descriptions do not save you

An agent answering "will this fit my table" is not summarising your story about craftsmanship. It is looking for a dimension. If the dimension is a paragraph, it is not a field, and the agent treats it as unknown.

The practical rule: **if a buyer asks it twice, it belongs in a field.**

## The 40-minute pass

- Export your catalog to CSV.
- For each of the ten fields, count blanks. Sort by revenue, not by SKU count.
- Fix the top 20 products by revenue first; that is usually 80% of agent-visible queries.
- Re-export and spot-check three products by asking the agent the same question a customer would.

## What agents do with partial data

- Missing size → "I can't confirm the fit."
- Missing compatibility → "Check with the seller."
- Missing contents → "The listing doesn't say."

Every one of those is a lost sale that looks like a bad model, not a bad feed.

## Where this becomes revenue

The [$99 catalog readiness audit](https://xynex.sekai.center/services) runs these ten fields across a CSV export and returns a scored sheet with the exact blanks to fill, in English or Chinese, three business days. No store login.

If you sell into the EU, pair it with the [$59 checkout check](https://xynex.sekai.center/guides/eu-checkout-rules) — the feed gets you found, the checkout gets you paid.

## FAQ

### Do I need a special feed format?
No. The attributes matter more than the format; most platforms accept a CSV with these fields.

### How often should I re-check?
Quarterly, and after any catalog import. New SKUs usually arrive with the same blanks.

### What does it cost?
The catalog audit is $99 per catalog. The template pack, if you run agents on the store too, is $9.99/month at the founding price. See the [pricing page](https://xynex.sekai.center/pricing).

```json-ld
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {"@type": "Question", "name": "Do I need a special feed format?", "acceptedAnswer": {"@type": "Answer", "text": "No. The attributes matter more than the format; most platforms accept a CSV with these fields."}},
    {"@type": "Question", "name": "How often should I re-check?", "acceptedAnswer": {"@type": "Answer", "text": "Quarterly, and after any catalog import. New SKUs usually arrive with the same blanks."}},
    {"@type": "Question", "name": "What does it cost?", "acceptedAnswer": {"@type": "Answer", "text": "The catalog audit is 99 USD per catalog. The template pack is 9.99 USD per month at the founding price. Details: https://xynex.sekai.center/pricing"}}
  ]
}
```
