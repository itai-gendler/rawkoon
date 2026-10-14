---
availability:
- {place: 'web::household'}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/library/libraryListRoutes.ts}
- {kind: code, role: implementation, target: apps/api/src/routes/books/bookListRoutes.ts}
- {kind: code, role: implementation, target: apps/web/src/pages/medias/_component/LibraryActionsSection.tsx}
---

# Remove from library

An administrator removes a movie, show or book from the library. Files stay on disk unless the administrator asks otherwise, and finished torrents keep seeding until their target unless removed now.
