---
availability:
- {place: 'web::household'}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/library/libraryFilesRoutes.ts}
- {kind: code, role: implementation, target: apps/api/src/services/downloadOutcome.ts#enqueuePostProcess}
---

# Retry ingest

An administrator queues the import of a finished download again after it failed.
