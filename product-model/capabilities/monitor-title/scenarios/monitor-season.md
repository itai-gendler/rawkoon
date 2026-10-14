---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator chooses Monitor season
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::household::title
- text: The Product marks every episode of the season monitored
  kind: product
  actor: administrator
  entities:
  - {entity: episode, effect: changes, facts: [Monitored]}
  contexts:
    web:
      place: web::household::title
---

# Monitor a season

## Trigger

A season should be collected.

## Outcome

Every episode of the season is searched for when aired.
