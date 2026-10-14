---
availability:
- {place: 'web::household'}
references:
- {kind: code, role: implementation, target: apps/api/src/services/libraryAttentionSync.ts}
- {kind: code, role: implementation, target: apps/api/src/workers/syncLibraryAttentionAlerts.ts}
---

# Raise attention alerts

Every hour Rawkoon raises an attention alert for each movie, episode or season pack whose automatic grabbing is struggling or gave up, and closes alerts whose condition cleared.
