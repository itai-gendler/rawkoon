---
kind: primary
routes:
  web: Web
steps:
- text: The Product finds an open alert whose title is now downloading or downloaded
  kind: condition
  unattended: true
  entities:
  - {entity: attention-alert, effect: reads, facts: [Kind]}
  contexts:
    web:
      place: web::household::home
- text: The Product closes it as resolved
  kind: product
  entities:
  - {entity: attention-alert, effect: changes, from: Open, to: Resolved, facts: []}
  contexts:
    web:
      place: web::household::home
---

# Close a cleared alert

## Trigger

The problem went away.

## Outcome

The alert leaves the panel.
