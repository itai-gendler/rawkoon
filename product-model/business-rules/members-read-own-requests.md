---
appliesTo:
- {type: entity, id: request, effect: reads}
permits:
- {actors: [administrator]}
- {related: [{verb: requests, entity: member}]}
- {unattended: true}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/requests/index.ts}
---

# A member sees only their own requests; an administrator sees every request

The Requests page lists a member's own requests and an administrator's view of the whole household.
