---
domain: books
relations:
- {entity: book-file, verb: has, cardinality: one-to-many}
- {entity: grab, verb: has, cardinality: one-to-many}
- {entity: reading-progress, verb: has, cardinality: one-to-many}
references:
- {kind: code, role: implementation, target: apps/api/prisma/schema.prisma}
- {kind: doc, role: intent, target: CONTEXT.md, title: Edition}
---

# Ebook

A book's ebook edition, searched, graded and stored on its own.

## Information kept

- **Monitored** — whether automatic searches look for it
- **Quality profile** — the book quality profile for this edition
- **Search attempts** — automatic searches that found nothing suitable
- **Size on disk** — the size of its files

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
