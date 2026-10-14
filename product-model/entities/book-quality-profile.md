---
domain: books-settings
references:
- {kind: code, role: implementation, target: apps/api/src/routes/books/bookQualityProfileRoutes.ts}
- {kind: doc, role: intent, target: docs/library/books.md, title: Book quality profiles}
---

# Book quality profile

The rules that decide which ebook and audiobook releases are allowed and preferred.

## Information kept

- **Name** — a unique name
- **Kind** — ebook, audiobook or both; a profile for one kind is never used for the other
- **Allowed formats** — the formats allowed, best first
- **Cutoff format** — an edition at or above it is never searched for an upgrade again
- **Prefer retail** — whether retail releases rank higher
- **Maximum size** — releases above it are rejected
- **Minimum seeders** — releases below it are rejected when the indexer reports seeders
- **Minimum audio bitrate** — audiobook releases below it are rejected
- **Preferred languages** — languages that rank higher; the book's own language is always added
- **Prioritized trackers** — trackers in order of preference
- **Prefer tracker over quality** — whether tracker order outranks format
