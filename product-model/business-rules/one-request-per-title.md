---
appliesTo:
- {type: capability, id: request-title}
- {type: entity, id: request, effect: creates}
references:
- {kind: code, role: implementation, target: apps/api/src/services/mediaRequests.ts#createRequest}
---

# A title is requested once

A pending or approved request for a title answers everyone who asks; a denied one is reopened rather than duplicated.
