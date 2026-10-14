---
appliesTo:
- {type: entity, id: account, effect: changes, facts: [Password]}
permits:
- {actors: [administrator]}
- {related: [{verb: has, entity: member}]}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/users/index.ts}
- {kind: code, role: implementation, target: apps/api/src/routes/admin/adminUserRoutes.ts}
---

# A password is changed by the person who holds it or reset by an administrator

A person changes their own password with their current one; an administrator can set a new one for anyone.
