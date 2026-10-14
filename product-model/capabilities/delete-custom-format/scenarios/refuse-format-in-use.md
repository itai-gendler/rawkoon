---
kind: validation
routes:
  web: Web
steps:
- text: The Administrator deletes a custom format that profiles still use
  kind: actor
  actor: administrator
  entities:
  - {entity: custom-format, effect: reads, facts: []}
  contexts:
    web:
      place: web::administration::custom-formats
- text: The Product refuses while quality profiles use it
  kind: condition
  entities:
  - {entity: quality-profile, effect: reads, facts: [Custom formats]}
  contexts:
    web:
      place: web::administration::custom-formats
---

# Refuse a format still in use

## Trigger

A profile still scores the format.

## Outcome

The format stays.
