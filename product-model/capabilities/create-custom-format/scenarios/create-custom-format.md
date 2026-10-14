---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator names a custom format, adds its conditions and saves
  kind: actor
  actor: administrator
  entities:
  - {entity: custom-format, effect: reads, facts: []}
  contexts:
    web:
      place: web::administration::custom-formats
- text: The Product creates the custom format
  kind: product
  actor: administrator
  entities:
  - {entity: custom-format, effect: creates, facts: [Name, Conditions]}
  contexts:
    web:
      place: web::administration::custom-formats
---

# Create a custom format

## Trigger

A profile needs a rule the standard controls cannot express.

## Outcome

The format can be assigned to profiles.
