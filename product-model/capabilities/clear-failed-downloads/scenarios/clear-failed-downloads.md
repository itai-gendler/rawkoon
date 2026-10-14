---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator chooses Clear failures and confirms
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::household::title
- text: The Product deletes the title's failed grabs and grabs whose import failed, and resolves their open attention alerts
  kind: product
  actor: administrator
  entities:
  - {entity: grab, as: failed-grab, effect: removes, from: Failed}
  - {entity: grab, as: failed-import, effect: removes, from: Import failed}
  - {entity: attention-alert, effect: changes, from: Open, to: Resolved, facts: []}
  contexts:
    web:
      place: web::household::title
---

# Clear failures

## Trigger

A title's history is cluttered with old failures.

## Outcome

Only successful and running downloads remain.
