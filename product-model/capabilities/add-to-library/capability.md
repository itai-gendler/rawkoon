---
availability:
- {place: 'web::household'}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/library/libraryListRoutes.ts}
- {kind: code, role: implementation, target: apps/api/src/services/libraryFromTmdb.ts#addOrUpdateLibraryFromTmdb}
- {kind: code, role: implementation, target: apps/api/src/services/books/bookLibrary.ts#addBookFromVolume}
- {kind: code, role: implementation, target: apps/web/src/pages/books/_component/AddBookDialog.tsx}
- {kind: doc, role: intent, target: docs/getting-started.md, title: Add your first title}
---

# Add to library

An administrator adds a movie or show from TMDB, or a book from Google Books with the editions wanted, so Rawkoon starts looking for it. Adding books exists while the book library is turned on.
