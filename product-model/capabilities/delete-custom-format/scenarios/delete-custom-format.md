---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator deletes a custom format and confirms
  kind: actor
  actor: administrator
  entities:
  - {entity: custom-format, effect: reads, facts: []}
  contexts:
    web:
      place: web::administration::custom-formats
- text: The Product deletes the custom format
  kind: product
  actor: administrator
  entities:
  - {entity: custom-format, effect: removes}
  contexts:
    web:
      place: web::administration::custom-formats
---

# Delete a custom format

## Trigger

A format is no longer needed.

## Outcome

The format is gone.
