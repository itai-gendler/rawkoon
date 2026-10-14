---
domain: books
references:
- {kind: code, role: implementation, target: apps/api/src/routes/books/bookPlaybackRoutes.ts}
- {kind: doc, role: intent, target: docs/library/books.md, title: Progress}
---

# Listening position

Where a person is in an audiobook, kept on the server so every device resumes from it.

## Information kept

- **Position** — seconds into the whole-book timeline
- **Book length** — the length the position was recorded against
- **Finished** — whether the person reached the end
- **Updated** — when the device recorded it, never later than the server's clock
- **Device** — the device that recorded it
