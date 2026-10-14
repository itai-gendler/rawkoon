---
domain: notifications
references:
- {kind: code, role: implementation, target: apps/api/src/routes/notifications/index.ts}
- {kind: code, role: implementation, target: apps/api/src/workers/notificationService.ts}
---

# Notification

A message Rawkoon sends one person, shown in the app and pushed to their devices and channels.

## Information kept

- **Title** — the headline
- **Body** — the message
- **Kind** — what it is about, such as a request decided or a title downloaded
- **Link** — where opening it takes the person
- **Image** — the artwork shown with it
- **Received** — when it was sent

## States

### Unread

Not opened yet.

### Read

The person marked it read.
