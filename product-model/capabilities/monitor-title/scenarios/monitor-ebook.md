---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator turns Monitored on for an ebook
  kind: actor
  actor: administrator
  entities:
  - {entity: ebook, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::book
- text: The Product marks the edition monitored
  kind: product
  actor: administrator
  entities:
  - {entity: ebook, effect: changes, facts: [Monitored]}
  contexts:
    web:
      place: web::household::book
---

# Monitor a book edition

## Trigger

An edition should be searched for.

## Outcome

Scheduled book searches include the edition.
