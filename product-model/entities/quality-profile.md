---
domain: quality-profiles
references:
- {kind: code, role: implementation, target: apps/api/src/routes/quality-profiles/index.ts}
- {kind: doc, role: intent, target: docs/library/quality-profiles.md}
---

# Quality profile

The rules that decide which movie and show releases are allowed and which allowed release is preferred.

## Information kept

- **Name** — a unique name
- **Minimum resolution** — releases below it are rejected: 480, 720, 1080 or 2160
- **Resolution cutoff** — releases above it are rejected; reaching it means nothing better is wanted
- **Preferred sources** — sources in order of preference
- **Preferred codecs** — codecs in order of preference
- **Preferred languages** — audio languages a release title must mark; a release with none of them is rejected
- **Search title language** — the language of the title used in indexer searches for titles added with this profile
- **Prioritized trackers** — trackers in order of preference
- **Prefer tracker over quality** — whether tracker order outranks quality instead of breaking ties
- **Prefer HDR** — whether HDR releases rank higher
- **Require HDR** — whether releases without an HDR marker are rejected
- **Maximum size** — releases above it are rejected
- **Minimum seeders** — releases below it are rejected when the indexer reports seeders
- **Grab delay** — minutes an automatic grab waits after a release is published, to collect better ones
- **Skip delay at cutoff** — whether a release that already meets the cutoff is grabbed without waiting
- **Custom formats** — the custom formats assigned, each with a score, or marked required or forbidden
