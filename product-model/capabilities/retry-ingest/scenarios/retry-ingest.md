---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator chooses Retry ingest on a finished download that failed to import
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::household::home
- text: The Product queues the import again
  kind: product
  actor: administrator
  entities:
  - {entity: grab, effect: changes, from: Import failed, to: Completed, facts: [Import error]}
  contexts:
    web:
      place: web::household::home
---

# Retry an import

## Trigger

The cause of an import failure was fixed, such as a path mapping.

## Outcome

The import runs again.
