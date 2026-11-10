
# Podcast Transcript Feeds: The 20-Minute Fix Almost No Show Does

Transcripts make a show searchable, quotable and readable by assistants. The tag that publishes them has been available for years. Most shows still do not have it.

Five fields, one block in the RSS feed, twenty minutes.

## The five fields

1. **URL** — a plain text or VTT file, publicly reachable, no login.
2. **Type** — `text/plain` or `text/vtt`, matching the file.
3. **Language** — the actual language of the audio, per episode.
4. **Relationship** — `captions` if it is a verbatim transcript, `description` if it is a summary.
5. **Per-episode, not per-show** — one tag per item, because languages and quality differ.

## The block

```xml
<item>
  <title>Episode 12 — approval gates</title>
  <enclosure url="/ep12.mp3" type="audio/mpeg" length="12345"/>
  <podcast:transcript
    url="/ep12.vtt"
    type="text/vtt"
    language="en"
    rel="captions"/>
</item>
```

One namespace declaration at the top of the feed:

```xml
<rss version="2.0" xmlns:podcast="podcastindex.org/namespace/1.0">
```

That is the whole implementation.

## Why shows skip it

- The transcript exists but lives in a Google Doc.
- The hosting platform has no field for it.
- Someone tried once, the URL 404'd, and nobody checked again.

The third one is the most common. A dead URL is worse than no tag: apps cache the failure.

## The three checks that prove it works

1. **Fetch the URL from a clean session.** No cookies, no login. If it asks for anything, it fails.
2. **Validate the feed.** A namespace typo makes the block invisible without breaking the feed.
3. **Open the show in one app that supports transcripts.** If the text does not appear, the tag is wrong, not the app.

## What transcripts actually buy you

- Search: episode text becomes findable on the open web.
- Assistants: a readable source instead of an audio blob.
- Reuse: chapters, quotes, show notes, short posts, all from the same file.
- Accessibility: the one audience most shows still ignore.

## A realistic workflow

1. Transcribe with whatever tool you already pay for.
2. Convert to VTT if you want timestamps; plain text is enough for readability.
3. Upload to a public bucket or your site, one file per episode.
4. Add the tag to the item with the right language and `rel`.
5. Re-validate, then fetch the URL once from a fresh browser profile.

Twenty minutes for the first episode, two minutes for each one after.

## Where this becomes a service

The [$99 podcast transcript feed setup](https://xynex.sekai.center/services) does it for your back catalogue: transcript files generated or converted, tags added per episode, feed validated, and a screenshot per platform that reads it. Three business days, no hosting login — the RSS URL is enough.

If you also publish the show notes as articles, the [guide library](https://xynex.sekai.center/articles) covers the other half: making the text rank.

## FAQ

### Do I need to host the transcript myself?
Yes, or on any public URL. The feed points at a file; it does not store it.

### Plain text or VTT?
VTT if you want timestamps and player sync. Plain text if you only want search and readability.

### What does the setup cost?
$99 for a back catalogue. See the [pricing page](https://xynex.sekai.center/pricing) for the template pack if you also run agents on the business.

```json-ld
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {"@type": "Question", "name": "Do I need to host the transcript myself?", "acceptedAnswer": {"@type": "Answer", "text": "Yes, or on any public URL. The feed points at a file; it does not store it."}},
    {"@type": "Question", "name": "Plain text or VTT?", "acceptedAnswer": {"@type": "Answer", "text": "VTT if you want timestamps and player sync. Plain text if you only want search and readability."}},
    {"@type": "Question", "name": "What does the setup cost?", "acceptedAnswer": {"@type": "Answer", "text": "99 USD for a back catalogue. Details: https://xynex.sekai.center/pricing"}}
  ]
}
```
