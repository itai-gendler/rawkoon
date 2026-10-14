---
domain: books
relations:
- {entity: ebook, verb: has, cardinality: one-to-one}
- {entity: audiobook, verb: has, cardinality: one-to-one}
- {entity: read-badge, verb: has, cardinality: one-to-many}
references:
- {kind: code, role: implementation, target: apps/api/prisma/schema.prisma}
- {kind: code, role: implementation, target: apps/api/src/services/books/bookLibrary.ts#addBookFromVolume}
- {kind: doc, role: intent, target: docs/library/books.md}
---

# Book

A book in the library: one catalog volume, with up to two editions, an ebook and an audiobook. A translation is a book of its own.

## Information kept

- **Title** — the book's title, merged from the metadata sources or set by hand
- **Subtitle** — the subtitle
- **Authors** — the people who wrote it
- **Overview** — the description
- **Cover** — the cover image
- **Language** — the language the book is written in
- **Published** — the publication date or year
- **Series** — the series and the book's position in it
- **Narrators** — who narrates the audiobook
- **Genres** — the genres one source supplied
- **Publisher** — the publisher
- **Page count** — the number of pages
- **Rating** — the rating and how many people rated it
- **ISBN** — the ISBN
- **Catalog identity** — the Google Books volume it was added from; the library holds a volume once
- **Metadata sources** — which source supplied each field
- **Added** — when it joined the library
