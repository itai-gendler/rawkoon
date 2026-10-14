---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator names a profile, picks its kind and orders the allowed formats, best first, and saves
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::administration::books-settings
- text: The Product creates the profile
  kind: product
  actor: administrator
  entities:
  - {entity: book-quality-profile, effect: creates, facts: [Name, Kind, Allowed formats, Cutoff format, Prefer retail, Maximum size, Minimum seeders, Minimum audio bitrate, Preferred languages, Prioritized trackers, Prefer tracker over quality]}
  contexts:
    web:
      place: web::administration::books-settings
---

# Create a book quality profile

## Trigger

Some books need different format rules.

## Outcome

The profile can be given to editions of its kind.
