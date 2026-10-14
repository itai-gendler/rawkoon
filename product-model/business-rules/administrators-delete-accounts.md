---
appliesTo:
- {type: entity, id: account, effect: removes}
permits:
- {actors: [administrator]}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/admin/adminUserRoutes.ts}
---

# Only an administrator deletes an account

There is no self-service account deletion.
