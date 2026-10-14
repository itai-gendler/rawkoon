---
appliesTo:
- {type: capability, id: mark-book-read}
- {type: entity, id: read-badge}
references:
- {kind: code, role: implementation, target: apps/api/src/services/books/setBookRead.ts#setBookRead}
---

# Marking a book read resets the person's progress in its editions

The Read badge means the book is done; the next listen or read starts over.
