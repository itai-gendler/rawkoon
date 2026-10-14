---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator changes a profile's rules and saves
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::administration::quality-profiles
- text: The Product saves the profile
  kind: product
  actor: administrator
  entities:
  - {entity: quality-profile, effect: changes, facts: [Name, Minimum resolution, Resolution cutoff, Preferred sources, Preferred codecs, Preferred languages, Search title language, Prioritized trackers, Prefer tracker over quality, Prefer HDR, Require HDR, Maximum size, Minimum seeders, Grab delay, Skip delay at cutoff, Custom formats]}
  contexts:
    web:
      place: web::administration::quality-profiles
---

# Edit a quality profile

## Trigger

A profile lets through releases the household does not want, or rejects too many.

## Outcome

Every title with the profile is searched by the new rules.
