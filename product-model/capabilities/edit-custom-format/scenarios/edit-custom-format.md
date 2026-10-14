---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator changes a custom format's conditions and saves
  kind: actor
  actor: administrator
  entities:
  - {entity: custom-format, effect: reads, facts: []}
  contexts:
    web:
      place: web::administration::custom-formats
- text: The Product saves the custom format
  kind: product
  actor: administrator
  entities:
  - {entity: custom-format, effect: changes, facts: [Name, Conditions]}
  contexts:
    web:
      place: web::administration::custom-formats
---

# Edit a custom format

## Trigger

A format matches too much or too little.

## Outcome

Profiles using it score releases by the new conditions.
