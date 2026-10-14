---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator turns on Monitor for an author on Authors
  kind: actor
  actor: administrator
  entities:
  - {entity: author, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::authors
- text: The Product marks the author monitored from today
  kind: product
  actor: administrator
  entities:
  - {entity: author, effect: changes, facts: [Monitored, Monitored from]}
  contexts:
    web:
      place: web::household::authors
---

# Monitor an author

## Trigger

The household wants everything new an author writes.

## Outcome

Titles the author publishes from today on are added; the backlist is not.
