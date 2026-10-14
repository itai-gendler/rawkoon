---
appliesTo:
- {type: entity, id: account, effect: changes, facts: [First name, Last name, Avatar, Notification preferences]}
permits:
- {related: [{verb: has, entity: member}]}
- {related: [{verb: has, entity: administrator}]}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/users/index.ts}
---

# A person changes only their own profile and notification preferences

Names, profile picture and which notifications to receive are the person's own.
