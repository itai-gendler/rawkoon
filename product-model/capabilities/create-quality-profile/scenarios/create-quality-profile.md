---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator fills in a new profile's rules and preferences, giving scored formats their weight, and saves
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::administration::quality-profiles
- text: The Product creates the profile
  kind: product
  actor: administrator
  entities:
  - {entity: quality-profile, effect: creates, facts: [Name, Minimum resolution, Resolution cutoff, Preferred sources, Preferred codecs, Preferred languages, Search title language, Prioritized trackers, Prefer tracker over quality, Prefer HDR, Require HDR, Maximum size, Minimum seeders, Grab delay, Skip delay at cutoff, Custom formats]}
  contexts:
    web:
      place: web::administration::quality-profiles
---

# Create a quality profile

## Trigger

The household wants different release rules for some titles.

## Outcome

The profile can be assigned to titles and set as a default.
