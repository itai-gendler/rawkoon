---
appliesTo:
- {type: entity, id: account, effect: changes, facts: [Administrator access]}
permits:
- {actors: [administrator]}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/admin/adminUserRoutes.ts}
---

# Only an administrator changes a person's role

Who administers the instance is decided by its administrators.
