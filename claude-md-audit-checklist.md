
# A 12-Point CLAUDE.md Audit You Can Run in 20 Minutes

An audit is not a vibe check. Each of these twelve points has a test you can run in under two minutes, and a clear pass condition.

Score one point per pass, half per warning. 10+ is usable, 6–9 is fragile, under 6 will produce silent failures.

## 1. One file, one owner
**Test:** search the repo for other copies. `find . -name "CLAUDE.md" -o -name "AGENTS.md"`
**Pass:** one authority file, one named owner, no per-repo forks.

## 2. Scope boundary
**Test:** count prohibitions. `grep -ciE "never|do not|must not" CLAUDE.md`
**Pass:** at least three, each naming a concrete action.

## 3. Gate list
**Test:** search for the five money actions: post, email, price, refund, deploy.
**Pass:** all five appear with a rule and who may pass them.

## 4. Definition of done
**Test:** search `grep -i "done" CLAUDE.md`
**Pass:** a sentence that defines done as artifact plus check plus next step.

## 5. Status format
**Test:** search for the three labels.
**Pass:** `done / open / next` appears with an example.

## 6. Secrets hygiene
**Test:** `grep -iE "key|token|secret|\\.env" CLAUDE.md`
**Pass:** the rule says variable names only, and stops before printing env values.

## 7. Precedence
**Test:** search for conflict or priority language.
**Pass:** an explicit order, e.g. safety > money > speed.

## 8. Question policy
**Test:** search for "ask".
**Pass:** a limit (one question) and a rule for when it is allowed.

## 9. Output path
**Test:** does the file say where work lands?
**Pass:** a folder or naming convention, not "the user's workspace".

## 10. Context budget
**Test:** `wc -w CLAUDE.md`
**Pass:** under 700 words. Over 1,200 is a fail: it costs tokens on every task.

## 11. No stale placeholders
**Test:** `grep -nE "\\{\\{|TODO|TBD" CLAUDE.md`
**Pass:** none, or a dated note saying what fills them.

## 12. Honesty rule
**Test:** search for invented numbers.
**Pass:** a line banning fabricated metrics, reviews, customers and revenue.

## What the scores mean in practice

Teams usually fail 4, 5, 8 and 10. That combination is exactly the "agent says done and nothing changed" pattern: no definition of done, no status format, unlimited questions, and a file so long nobody reads it.

Fix those four first. Most teams gain more from that than from any new tool.

## Run it automatically

The free [score tool](https://xynex.sekai.center/check) runs these checks on a pasted file and names the three to fix first. For a team, the [$299 audit](https://xynex.sekai.center/audit) adds line-by-line scoring across every member's file, one corrected version, a delete list and a recording. If you only need one file fixed, the [$29 context fix](https://xynex.sekai.center/org-skills) returns it in 24 hours.

## FAQ

### How often should I re-run the audit?
Every time a rule changes, and once a quarter. Otherwise the file drifts back to prose.

### Can I audit a file I did not write?
Yes. The checks are about structure and specificity, not style.

### What does the pack cost?
$9.99 per month at the founding price, or $79 per year. It moves to $19.99 on 2026-12-01. Details on the [pricing page](https://xynex.sekai.center/pricing).

```json-ld
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {"@type": "Question", "name": "How often should I re-run the audit?", "acceptedAnswer": {"@type": "Answer", "text": "Every time a rule changes, and once a quarter. Otherwise the file drifts back to prose."}},
    {"@type": "Question", "name": "Can I audit a file I did not write?", "acceptedAnswer": {"@type": "Answer", "text": "Yes. The checks are about structure and specificity, not style."}},
    {"@type": "Question", "name": "What does the pack cost?", "acceptedAnswer": {"@type": "Answer", "text": "9.99 USD per month at the founding price, or 79 USD per year. It moves to 19.99 USD on 2026-12-01. Details: https://xynex.sekai.center/pricing"}}
  ]
}
```
