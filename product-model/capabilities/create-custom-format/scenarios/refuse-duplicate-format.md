---
kind: validation
routes:
  web: Web
steps:
- text: The Administrator saves a custom format under a name another format has
  kind: actor
  actor: administrator
  entities:
  - {entity: custom-format, effect: reads, facts: []}
  contexts:
    web:
      place: web::administration::custom-formats
- text: The Product refuses
  kind: condition
  entities:
  - {entity: custom-format, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::administration::custom-formats
---

# Refuse a name already used

## Trigger

Two formats would share a name.

## Outcome

No format is created.
