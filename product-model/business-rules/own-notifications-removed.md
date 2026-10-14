---
appliesTo:
- {type: entity, id: notification, effect: removes}
permits:
- {related: [{verb: receives, entity: account}, {verb: has, entity: member}]}
- {related: [{verb: receives, entity: account}, {verb: has, entity: administrator}]}
- {unattended: true}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/notifications/index.ts}
- {kind: code, role: implementation, target: apps/api/src/workers/cleanupNotifications.ts}
---

# A person deletes only their own notifications

Notifications are addressed to one person.
