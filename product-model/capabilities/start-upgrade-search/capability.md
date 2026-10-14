---
domain: library
availability:
- {place: 'web::household'}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/library/libraryGrabRoutes.ts}
- {kind: code, role: implementation, target: apps/web/src/pages/medias/_component/LibraryUpgradeModal.tsx}
- {kind: code, role: implementation, target: apps/api/src/workers/upgradeMediaSearch.ts}
---

# Start an upgrade search

From Upgrade Quality, an administrator has Rawkoon search for releases that meet a title's new profile, keeping the current files until better ones arrive.
