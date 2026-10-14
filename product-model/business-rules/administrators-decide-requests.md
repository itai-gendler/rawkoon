---
appliesTo:
- {type: entity, id: request, effect: changes, to: Approved}
- {type: entity, id: request, effect: changes, to: Denied}
permits:
- {actors: [administrator]}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/requests/index.ts}
---

# Only an administrator approves or denies a request

A request is the household's ask; the decision is the administrator's.
