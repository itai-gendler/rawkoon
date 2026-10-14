---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator changes a book quality profile's formats or preferences and saves
  kind: actor
  actor: administrator
  entities:
  - {entity: book-quality-profile, effect: reads, facts: []}
  contexts:
    web:
      place: web::administration::books-settings
- text: The Product saves the profile
  kind: product
  actor: administrator
  entities:
  - {entity: book-quality-profile, effect: changes, facts: [Name, Kind, Allowed formats, Cutoff format, Prefer retail, Maximum size, Minimum seeders, Minimum audio bitrate, Preferred languages, Prioritized trackers, Prefer tracker over quality]}
  contexts:
    web:
      place: web::administration::books-settings
---

# Edit a book quality profile

## Trigger

A book profile needs different rules.

## Outcome

Editions with the profile are searched by the new rules.
