---
kind: primary
routes:
  web: Web
steps:
- text: The Member marks a notification read
  kind: actor
  actor: member
  entities:
  - {entity: notification, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::notifications
- text: The Product marks it read
  kind: product
  actor: member
  entities:
  - {entity: notification, effect: changes, from: Unread, to: Read, facts: []}
  contexts:
    web:
      place: web::household::notifications
---

# Mark a notification read

## Trigger

A person has seen it.

## Outcome

The unread count drops.
