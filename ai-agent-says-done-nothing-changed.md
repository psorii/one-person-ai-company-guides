
# Why Your AI Agent Says "Done" and Nothing Changed

"Done."

You open the folder. No file. No test. No commit. The agent is not lying — it is answering a different question than the one you asked. You asked for work; it reported on its own confidence.

This is the most expensive failure mode in agent work, because it looks like progress. You move on to the next task, and three days later you discover nothing shipped.

## The cause: no definition of done

A human team does not argue about what "done" means, because the definition is written down: the pull request is merged, the tests pass, the page is live. An agent without that definition falls back to the only signal it has: whether its own answer sounds complete.

Fix the definition and the behaviour changes without touching the model.

## The three-part definition

Work is done when all three exist:

1. **A file.** Not a plan for a file. The artifact, at a path you can open.
2. **A check.** A test, a script, a `curl` that returns the expected thing, or a screenshot at two widths. Something that would fail if the work were fake.
3. **A next step.** One line: what happens now, or what is blocked and on whom.

If any of the three is missing, the answer is "not done", and the agent says which part is missing.

## The status format that enforces it

Every step ends with three lines:

```
done: <files touched + what changed>
open: <what is not finished>
next: <one action, or the block>
```

Three rules make this work:

- **Paths, not adjectives.** "`public/pricing.html`, hero + 2 buy buttons" beats "improved the pricing page".
- **`open:` cannot be empty if anything is unfinished.** An empty `open:` with a half-built feature is a false report.
- **`next:` must be executable by someone else.** If only the author understands it, it is not a next step.

Put this format in your `CLAUDE.md` (or `AGENTS.md`) so every session inherits it, and ask for it in the brief. You will stop reading chat logs and start reading status notes.

## Why "I checked it" is not a check

Agents can look at a 2,000-row CSV and say it looks right. That is not a check; it is an impression. A check is a command with an exit code, or a diff you can inspect.

Cheap checks that catch most fake completions:

- `node tools/selftest.mjs` — your own test file, exit code non-zero on failure
- `grep -c "<expected string>" file` — proves the change landed
- `curl -s -o /dev/null -w '%{http_code}' URL` — proves the page is live
- a screenshot at 390 px and 1280 px — proves the layout did not break
- `git diff --stat` — proves which files moved

None of these require trust. That is the point.

## The failure that costs the most

The expensive version is not the agent that says "done" with nothing. It is the agent that says "done", you believe it, and you **publish** it: a post with a broken link, a price page with two different prices, an email to a customer with the wrong number.

That is why the status format belongs next to an approval gate. The gate answers "may this leave the folder?"; the status note answers "what actually happened?". You need both.

## A five-minute retrofit

1. Add the three-line format to `CLAUDE.md`.
2. Add one line: "Done requires a file, a check and a next step."
3. Ask for it in the brief of your next task, not all of them.
4. After the task, read only the status note. If it is vague, the brief was vague.

Do this once and every later session inherits it. That is the difference between five agents and five chat windows.

---

*This is one of the gates in the One-Person AI Company Pack: 39 files, 5 roles, 6 checklists, 7 prompts, 3 filled examples, English and Chinese.*

## FAQ

### Does this work with any agent?
Yes. The format is plain Markdown; Claude Code reads `CLAUDE.md`, Codex and most others read `AGENTS.md`.

### What if my agent still says "done" with no file?
Make the brief ask for the three lines, then reject any answer where `done:` has no path. Two rounds is usually enough.

### What does the pack cost?
US$9.99/month at the founding price, cancel in one click. See the [pricing page](https://xynex.sekai.center/pricing).

```json-ld
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {"@type": "Question", "name": "Does this work with any agent?", "acceptedAnswer": {"@type": "Answer", "text": "Yes. The format is plain Markdown; Claude Code reads CLAUDE.md, Codex and most others read AGENTS.md."}},
    {"@type": "Question", "name": "What if my agent still says \"done\" with no file?", "acceptedAnswer": {"@type": "Answer", "text": "Make the brief ask for the three lines, then reject any answer where done has no path. Two rounds is usually enough."}},
    {"@type": "Question", "name": "What does the pack cost?", "acceptedAnswer": {"@type": "Answer", "text": "US$9.99 per month at the founding price, cancel in one click. Details: https://xynex.sekai.center/pricing"}}
  ]
}
```
