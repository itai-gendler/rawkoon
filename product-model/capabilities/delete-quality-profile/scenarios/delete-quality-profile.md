---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator deletes a profile and confirms
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::administration::quality-profiles
- text: The Product deletes the profile
  kind: product
  actor: administrator
  entities:
  - {entity: quality-profile, effect: removes}
  contexts:
    web:
      place: web::administration::quality-profiles
---

# Delete a quality profile

## Trigger

A profile is no longer needed.

## Outcome

The profile is gone.
