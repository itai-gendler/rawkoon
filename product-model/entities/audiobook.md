---
domain: books
relations:
- {entity: book-file, verb: has, cardinality: one-to-many}
- {entity: grab, verb: has, cardinality: one-to-many}
- {entity: listening-progress, verb: has, cardinality: one-to-many}
- {entity: downloaded-audiobook, verb: has, cardinality: one-to-many}
references:
- {kind: code, role: implementation, target: apps/api/prisma/schema.prisma}
- {kind: doc, role: intent, target: CONTEXT.md, title: Chapter}
---

# Audiobook

A book's audiobook edition, searched, graded and stored on its own, and played chapter by chapter.

## Information kept

- **Monitored** — whether automatic searches look for it
- **Quality profile** — the book quality profile for this edition
- **Search attempts** — automatic searches that found nothing suitable
- **Size on disk** — the size of its files
- **Narrators** — the narrators read from the audio files' tags
- **Duration** — the length of the whole book
- **Chapters** — the chapters on the whole-book timeline, each with its title and where it starts and ends
- **Offline ready** — whether it has chapter files the iPhone app can download

## States

### Wanted

Missing from the library and eligible for searching while monitored.

### Downloading

A release was grabbed and is in the download client.

### Downloaded

A file is in the library.

### Upgrading

A better release was grabbed while the current file stays in place.

### Skipped

Automatic searching gave up after repeated misses; a manual search or Retry search makes it wanted again.
