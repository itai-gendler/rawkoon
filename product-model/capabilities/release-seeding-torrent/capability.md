---
availability:
- {place: 'web::administration'}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/downloads/index.ts}
- {kind: code, role: implementation, target: apps/api/src/services/seeding/seedSweep.ts}
- {kind: code, role: implementation, target: apps/web/src/pages/library/downloads.tsx}
---

# Remove a seeding torrent

Rawkoon removes a finished torrent from the download client once it has seeded to its target, and an administrator can remove one sooner. Rawkoon only removes torrents it added and no other title still owns.
