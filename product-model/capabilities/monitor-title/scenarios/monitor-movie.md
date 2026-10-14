---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator chooses Monitor on an unmonitored movie
  kind: actor
  actor: administrator
  entities:
  - {entity: movie, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
- text: The Product marks the movie monitored
  kind: product
  actor: administrator
  entities:
  - {entity: movie, effect: changes, facts: [Monitored]}
  contexts:
    web:
      place: web::household::title
---

# Monitor a movie

## Trigger

A title should be searched for again.

## Outcome

Scheduled searches and RSS include the movie.
