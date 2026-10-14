---
domain: books
relations:
- {entity: book, verb: writes, cardinality: many-to-many}
references:
- {kind: code, role: implementation, target: apps/api/prisma/schema.prisma}
- {kind: doc, role: intent, target: docs/library/books.md, title: Following an author}
---

# Author

A book author, known by name. Two writers with the same name are one author.

## Information kept

- **Name** — the author's name
- **Photo** — the author's picture
- **Biography** — a short biography
- **Monitored** — whether new titles by the author are added automatically
- **Monitored from** — the date monitoring was switched on; only titles published on or after it are added
- **Editions to add** — the editions new titles arrive as; ebooks when none is chosen
- **Languages** — the languages a new title must be in to be added; any language when none is chosen
- **Quality profile** — the book quality profile new titles receive
- **Last checked** — when Rawkoon last looked for new titles
