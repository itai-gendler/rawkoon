---
domain: requests
availability:
- {place: 'web::household'}
- {place: 'iphone::household'}
references:
- {kind: code, role: implementation, target: apps/api/src/services/mediaRequests.ts#denyRequest}
---

# Deny a request

An administrator turns down a pending request, optionally with a reason the requester sees.
