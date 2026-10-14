---
kind: validation
routes:
  web: Web
steps:
- text: The Administrator deletes a profile assigned to library titles
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::administration::quality-profiles
- text: The Product refuses while titles are assigned to it
  kind: condition
  entities:
  - {entity: movie, effect: reads, facts: [Quality profile]}
  contexts:
    web:
      place: web::administration::quality-profiles
---

# Refuse a profile still in use

## Trigger

Titles still use the profile.

## Outcome

The profile stays.
