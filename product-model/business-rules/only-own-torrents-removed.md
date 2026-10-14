---
appliesTo:
- {type: capability, id: release-seeding-torrent}
- {type: capability, id: remove-from-library}
- {type: capability, id: track-downloads}
references:
- {kind: code, role: implementation, target: apps/api/src/services/seeding/seedSweep.ts}
- {kind: code, role: implementation, target: apps/api/src/services/downloadOutcome.ts#adoptDownload}
---

# Rawkoon removes only torrents it added that no other title still owns

A torrent the household added by hand is imported but never removed, and a torrent another title shares is kept.
