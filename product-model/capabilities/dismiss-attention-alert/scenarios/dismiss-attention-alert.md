---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator chooses Dismiss on an alert in Library attention
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::household::home
- text: The Product closes the alert as dismissed
  kind: product
  actor: administrator
  entities:
  - {entity: attention-alert, effect: changes, from: Open, to: Dismissed, facts: []}
  contexts:
    web:
      place: web::household::home
---

# Dismiss an alert

## Trigger

An administrator has dealt with it or does not care.

## Outcome

The alert leaves the panel.
