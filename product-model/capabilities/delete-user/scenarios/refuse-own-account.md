---
kind: validation
routes:
  web: Web
steps:
- text: The Administrator tries to delete their own account
  kind: actor
  actor: administrator
  entities:
  - {entity: account, effect: reads, facts: []}
  contexts:
    web:
      place: web::administration::users
- text: The Product refuses
  kind: condition
  entities: []
  contexts:
    web:
      place: web::administration::users
---

# Refuse deleting one's own account

## Trigger

An administrator picks themselves.

## Outcome

Their account stays.
