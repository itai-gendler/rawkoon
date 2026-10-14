---
availability:
- {place: 'web::household'}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/library/libraryGrabRoutes.ts}
- {kind: code, role: implementation, target: apps/api/src/services/mediaGrabberGrab.ts#grabRelease}
- {kind: code, role: implementation, target: apps/api/src/services/mediaGrabberAdopt.ts}
- {kind: code, role: implementation, target: apps/api/src/services/grabSpaceCheck.ts}
- {kind: doc, role: intent, target: docs/library/downloads-and-files.md}
---

# Grab a release

An administrator hands a chosen release to the download client for a movie, an episode, a season or a book edition. Rawkoon records the grab and follows it.
