---
kind: primary
routes:
  web: Web
steps:
- text: The Member deletes a notification
  kind: actor
  actor: member
  entities:
  - {entity: notification, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::notifications
- text: The Product deletes it
  kind: product
  actor: member
  entities:
  - {entity: notification, effect: removes, from: Read}
  contexts:
    web:
      place: web::household::notifications
---

# Delete a notification

## Trigger

A notification is no longer useful.

## Outcome

It is gone from the list.

## Edge cases

- Notifications older than thirty days are deleted nightly.
