---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator turns off Monitor for an author
  kind: actor
  actor: administrator
  entities:
  - {entity: author, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::authors
- text: The Product marks the author not monitored
  kind: product
  actor: administrator
  entities:
  - {entity: author, effect: changes, facts: [Monitored]}
  contexts:
    web:
      place: web::household::authors
---

# Unmonitor an author

## Trigger

New titles by the author are no longer wanted.

## Outcome

The author's new titles are no longer added.
