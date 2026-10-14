---
appliesTo:
- {type: capability, id: change-notification-preferences}
- {type: entity, id: notification, effect: creates}
references:
- {kind: code, role: implementation, target: apps/api/src/services/notificationPreferences.ts}
---

# A kind of notification a person turned off is not sent to them

Every kind is on until the person turns it off.
