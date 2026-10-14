---
domain: books
availability:
- {place: 'web::household'}
references:
- {kind: code, role: implementation, target: apps/api/src/services/books/setBookRead.ts#setBookRead}
---

# Mark a book read

A person marks a whole book read, which resets their progress in its editions.
