---
appliesTo:
- {type: entity, id: notification, effect: reads}
permits:
- {related: [{verb: receives, entity: account}, {verb: has, entity: member}]}
- {related: [{verb: receives, entity: account}, {verb: has, entity: administrator}]}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/notifications/index.ts}
---

# A person sees only their own notifications

Notifications are addressed to one person.
