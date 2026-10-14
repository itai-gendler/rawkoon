---
domain: books
availability:
- {place: 'web::household'}
references:
- {kind: code, role: implementation, target: apps/api/src/workers/checkAuthorReleases.ts}
- {kind: doc, role: intent, target: docs/library/books.md, title: Following an author}
---

# Add titles from followed authors

Once a day, with books on, Rawkoon adds new titles by each monitored author.
