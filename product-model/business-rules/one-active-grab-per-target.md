---
appliesTo:
- {type: capability, id: grab-release}
- {type: capability, id: search-now}
- {type: capability, id: search-wanted-titles}
- {type: entity, id: grab}
references:
- {kind: code, role: implementation, target: apps/api/src/services/mediaGrabberGrab.ts#grabRelease}
---

# A movie, episode, season or edition has at most one download running at a time

A second grab for the same target is refused until the running one is cancelled, however the grab was started.

## Rationale

Scheduled searches and RSS polling can fire on the same tick from the same wanted list; without the rule both would hand the same title to the client.
