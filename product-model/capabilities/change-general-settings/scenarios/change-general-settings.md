---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator changes the country, the look-ahead window or the languages and saves
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::administration::general-settings
- text: The Product saves them
  kind: product
  actor: administrator
  entities:
  - {entity: general-settings, effect: changes, facts: [Country, Upcoming window, Upcoming languages]}
  contexts:
    web:
      place: web::administration::general-settings
---

# Change general settings

## Trigger

The household is in another region.

## Outcome

Release dates and upcoming releases follow the new settings.
