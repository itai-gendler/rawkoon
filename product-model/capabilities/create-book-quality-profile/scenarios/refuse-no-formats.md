---
kind: validation
routes:
  web: Web
steps:
- text: The Administrator saves a profile with no allowed format
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::administration::books-settings
- text: The Product refuses
  kind: condition
  entities: []
  contexts:
    web:
      place: web::administration::books-settings
---

# Refuse a profile with no allowed format

## Trigger

Nothing would be allowed.

## Outcome

No profile is created.

## Edge cases

- A format that does not belong to the profile's kind is refused.
