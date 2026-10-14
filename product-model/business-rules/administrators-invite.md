---
appliesTo:
- {type: entity, id: invitation, effect: creates}
permits:
- {actors: [administrator]}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/admin/adminUserRoutes.ts}
---

# Only an administrator creates an invitation

Accounts come from administrators: by invitation or directly.
