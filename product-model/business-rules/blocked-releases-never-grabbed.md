---
appliesTo:
- {type: capability, id: grab-release}
- {type: capability, id: search-wanted-titles}
- {type: capability, id: grab-from-rss}
- {type: entity, id: blocklisted-release}
references:
- {kind: code, role: implementation, target: apps/api/src/services/mediaGrabberHelpers.ts#checkBlocklist}
---

# A blocked release is never grabbed

The blocklist is checked on every grab, manual or automatic.
