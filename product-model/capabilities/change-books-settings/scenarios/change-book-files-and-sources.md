---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator changes the naming templates, the default book quality profile or the order of metadata sources and saves
  kind: actor
  actor: administrator
  entities:
  - {entity: book-quality-profile, effect: reads, facts: []}
  contexts:
    web:
      place: web::administration::books-settings
- text: The Product saves them; a source taken out of the order is no longer asked
  kind: product
  actor: administrator
  entities:
  - {entity: library-settings, effect: changes, facts: [Book naming, Audiobook naming, Default book profile, Metadata source order]}
  contexts:
    web:
      place: web::administration::books-settings
---

# Change book naming and metadata sources

## Trigger

Book files or metadata should come out differently.

## Outcome

Later imports and refreshes follow the new settings.
