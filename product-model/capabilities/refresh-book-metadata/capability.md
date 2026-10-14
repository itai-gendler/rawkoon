---
domain: books
availability:
- {place: 'web::household'}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/books/bookMetadataRoutes.ts}
- {kind: doc, role: intent, target: docs/library/books.md, title: Metadata sources}
---

# Refresh book metadata

A book's details are merged again from the metadata sources in priority order, each field from the highest source that has it.
