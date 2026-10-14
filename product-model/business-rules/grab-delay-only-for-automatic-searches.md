---
appliesTo:
- {type: capability, id: search-wanted-titles}
- {type: capability, id: search-now}
- {type: entity, id: pending-release}
references:
- {kind: code, role: implementation, target: apps/api/src/services/mediaGrabberSearch.ts}
- {kind: code, role: implementation, target: apps/api/src/services/grabDelay.ts}
---

# Only scheduled searches wait for a profile's grab delay

Manual and upgrade searches grab at once; a release that already meets the cutoff skips the wait when the profile says so.
