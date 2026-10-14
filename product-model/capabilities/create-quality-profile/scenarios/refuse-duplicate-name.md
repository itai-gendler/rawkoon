---
kind: validation
routes:
  web: Web
steps:
- text: The Administrator saves a profile under a name another profile has
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::administration::quality-profiles
- text: The Product refuses
  kind: condition
  entities:
  - {entity: quality-profile, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::administration::quality-profiles
---

# Refuse a name already used

## Trigger

Two profiles would share a name.

## Outcome

No profile is created.

## Edge cases

- Resolutions other than 480, 720, 1080 and 2160 are refused.
