---
appliesTo:
- {type: capability, id: remove-from-library}
- {type: capability, id: release-seeding-torrent}
references:
- {kind: code, role: implementation, target: apps/api/src/services/seeding/seedSweep.ts}
---

# Finished torrents keep seeding until their target unless removed now

Removing a title from the library keeps its finished grabs so their torrents reach their seed targets; Rawkoon removes them once they do, when automatic release is on.
