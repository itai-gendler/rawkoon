---
kind: validation
routes:
  web: Web
steps:
- text: The Administrator tries to turn the library switch on with no provider key stored
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::administration::books-settings
- text: The Product keeps the switch inert until a key is stored
  kind: condition
  entities:
  - {entity: integration-settings, effect: reads, facts: [Google Books]}
  contexts:
    web:
      place: web::administration::books-settings
---

# Books stay off without a key

## Trigger

No key is stored.

## Outcome

Books stay off.
