---
appliesTo:
- {type: capability, id: track-downloads}
- {type: entity, id: request, effect: changes, to: Available}
references:
- {kind: code, role: implementation, target: apps/api/src/services/mediaRequests.ts#notifyRequestAvailable}
---

# A request becomes available when its title is downloaded

The requester is told once the movie, or for a show the whole series, is downloaded; a single finished episode does not complete a show's request.
