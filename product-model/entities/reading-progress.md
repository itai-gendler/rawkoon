---
domain: books
references:
- {kind: code, role: implementation, target: apps/api/src/routes/books/bookPlaybackRoutes.ts}
- {kind: doc, role: intent, target: docs/library/books.md, title: Progress}
---

# Reading position

Where a person is in an ebook, kept on the server so every device resumes from it.

## Information kept

- **Chapter path** — the chapter document the position is in; what a device trusts when the chapters were reordered
- **Chapter index** — the chapter's place in the book
- **Chapter count** — how many chapters the book had when recorded
- **Offset** — how far into the chapter, from 0 to 1
- **Finished** — whether the person reached the end
- **Updated** — when the device recorded it, never later than the server's clock
