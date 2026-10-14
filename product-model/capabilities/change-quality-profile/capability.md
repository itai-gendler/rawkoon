---
availability:
- {place: 'web::household'}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/library/libraryMetaRoutes.ts}
- {kind: code, role: implementation, target: apps/api/src/routes/books/bookEditionRoutes.ts}
- {kind: code, role: implementation, target: apps/web/src/pages/medias/_component/LibraryQualityProfileSection.tsx}
---

# Change quality profile

An administrator assigns a different quality profile to a movie, show or book edition. When a movie's or show's downloaded files fail the new profile, Rawkoon offers to upgrade them.
