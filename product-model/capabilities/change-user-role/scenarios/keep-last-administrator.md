---
kind: validation
routes:
  web: Web
steps:
- text: The Administrator tries to make the only administrator a regular user
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::administration::users
- text: The Product refuses because nobody would be left to administer the instance
  kind: condition
  entities:
  - {entity: account, effect: reads, facts: [Administrator access]}
  contexts:
    web:
      place: web::administration::users
---

# Keep the last administrator

## Trigger

Only one administrator is left.

## Outcome

The instance keeps its administrator.
