---
appliesTo:
- {type: entity, id: invitation, effect: changes, to: Revoked}
- {type: entity, id: invitation, effect: changes, facts: [Link, Expires]}
permits:
- {actors: [administrator]}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/admin/adminUserRoutes.ts}
---

# Only an administrator regenerates or revokes an invitation

An invitation's link is the administrator's to replace or withdraw.
