---
kind: primary
routes:
  web: Web
steps:
- text: The Member chooses to mark all notifications read
  kind: actor
  actor: member
  entities:
  - {entity: notification, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::notifications
- text: The Product marks every unread notification of the person read
  kind: product
  actor: member
  entities:
  - {entity: notification, effect: changes, from: Unread, to: Read, facts: []}
  contexts:
    web:
      place: web::household::notifications
---

# Mark all read

## Trigger

A person caught up.

## Outcome

Nothing is unread.
