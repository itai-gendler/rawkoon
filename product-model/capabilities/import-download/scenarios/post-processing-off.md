---
kind: edge
routes:
  web: Web
steps:
- text: The Product finds post-processing turned off when a download completes
  kind: condition
  unattended: true
  entities:
  - {entity: library-settings, effect: reads, facts: [Post-processing]}
  contexts:
    web:
      place: web::household::title
- text: The Product queues no import and leaves the grab completed
  kind: product
  entities:
  - {entity: grab, effect: reads, facts: [Completed]}
  contexts:
    web:
      place: web::household::title
---

# Post-processing is off

## Trigger

The administrator places files by hand.

## Outcome

The title counts as downloaded while its file stays where the client put it.
