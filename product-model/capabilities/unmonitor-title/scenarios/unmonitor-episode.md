---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator unmonitors one episode
  kind: actor
  actor: administrator
  entities:
  - {entity: episode, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
- text: The Product marks the episode unmonitored
  kind: product
  actor: administrator
  entities:
  - {entity: episode, effect: changes, facts: [Monitored]}
  contexts:
    web:
      place: web::household::title
---

# Unmonitor an episode

## Trigger

One episode is not wanted.

## Outcome

Automatic searches skip the episode.
