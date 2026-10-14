---
kind: validation
routes:
  web: Web
steps:
- text: The Administrator retries the import of a download that failed or has not finished
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::household::home
- text: The Product refuses; it also refuses while post-processing is off
  kind: condition
  entities:
  - {entity: grab, effect: reads, facts: [Completed]}
  - {entity: library-settings, effect: reads, facts: [Post-processing]}
  contexts:
    web:
      place: web::household::home
---

# Refuse a retry that cannot run

## Trigger

There is nothing to import.

## Outcome

Nothing is queued.
