---
entities:
- {entity: book, shows: [Title, Authors, Cover, Published]}
- {entity: ebook, shows: [Monitored]}
- {entity: audiobook, shows: [Monitored]}
- {entity: author, shows: [Name]}
references:
- {kind: code, role: implementation, target: apps/web/src/pages/books/_component/BooksPage.tsx}
- {kind: code, role: implementation, target: apps/web/src/pages/books/_component/AddBookDialog.tsx}
---

# Books

The book library, with each book's ebook and audiobook state, and Add a book for administrators. It exists while the book library is turned on.
