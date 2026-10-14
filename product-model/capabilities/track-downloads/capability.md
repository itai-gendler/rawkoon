---
availability:
- {place: 'web::household'}
references:
- {kind: code, role: implementation, target: apps/api/src/workers/checkDownloadCompletion.ts}
- {kind: code, role: implementation, target: apps/api/src/services/downloadOutcome.ts#completeDownload}
- {kind: code, role: implementation, target: apps/api/src/services/downloadOutcome.ts#failDownload}
- {kind: code, role: implementation, target: apps/api/src/services/downloadJanitor.ts#rejectRelease}
- {kind: code, role: implementation, target: apps/api/src/services/mediaRequests.ts#notifyRequestAvailable}
- {kind: doc, role: intent, target: CONTEXT.md, title: Reconcile}
---

# Track downloads

Rawkoon checks the download client about every twenty seconds while downloads are moving, and less often when idle, and decides for each grab whether it finished, failed, stalled or should keep waiting.
