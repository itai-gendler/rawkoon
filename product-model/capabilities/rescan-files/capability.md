---
availability:
- {place: 'web::household'}
references:
- {kind: code, role: implementation, target: apps/api/src/services/library/rescan.ts#rescanLibraryItem}
- {kind: code, role: implementation, target: apps/api/src/routes/books/bookEditionRoutes.ts}
- {kind: doc, role: intent, target: docs/library/metadata.md, title: Rescan after changing files}
---

# Rescan files

An administrator has Rawkoon check a title's or edition's files on disk against the library: rescanning them, dropping records whose file is gone and adopting files already in place.
