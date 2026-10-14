---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator chooses Unmonitor on a movie
  kind: actor
  actor: administrator
  entities:
  - {entity: movie, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
- text: The Product marks the movie unmonitored
  kind: product
  actor: administrator
  entities:
  - {entity: movie, effect: changes, facts: [Monitored]}
  contexts:
    web:
      place: web::household::title
---

# Unmonitor a movie

## Trigger

A title should not be grabbed automatically.

## Outcome

Scheduled searches and RSS skip the movie; a manual search still works.
