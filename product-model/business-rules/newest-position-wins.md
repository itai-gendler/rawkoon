---
appliesTo:
- {type: capability, id: listen-to-audiobook}
- {type: capability, id: read-ebook}
- {type: entity, id: listening-progress}
- {type: entity, id: reading-progress}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/books/bookPlaybackRoutes.ts}
- {kind: doc, role: intent, target: docs/library/books.md, title: Progress}
---

# The newest position wins

A device's clock is clamped to the server's, and a position recorded earlier than the one kept is dropped, so no device walks a person backwards.
