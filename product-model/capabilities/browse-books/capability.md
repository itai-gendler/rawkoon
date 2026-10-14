---
domain: books
availability:
- {place: 'web::household'}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/books/bookListRoutes.ts}
- {kind: code, role: implementation, target: apps/web/src/pages/books/_component/BooksPage.tsx}
- {kind: code, role: implementation, target: apps/web/src/pages/books/_component/BookDetailPage.tsx}
---

# Browse books

A signed-in person browses the book library, with each book's ebook and audiobook state, and opens a book. The book library exists while it is turned on.
