---
kind: validation
routes:
  web: Web
steps:
- text: The Member enters a wrong current password
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::household::profile
- text: The Product refuses and keeps the old password
  kind: condition
  entities:
  - {entity: account, effect: reads, facts: [Password]}
  contexts:
    web:
      place: web::household::profile
---

# Refuse a wrong current password

## Trigger

A person mistypes their current password.

## Outcome

The password is unchanged.
