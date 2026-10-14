---
kind: validation
routes:
  web: Web
steps:
- text: The Administrator grabs a release for a movie that already has a grab downloading
  kind: actor
  actor: administrator
  entities:
  - {entity: movie, effect: reads, facts: []}
  - {entity: grab, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
- text: The Product refuses until the active download is cancelled
  kind: condition
  entities:
  - {entity: grab, effect: reads, facts: [Release title]}
  contexts:
    web:
      place: web::household::title
---

# Refuse a second active grab

## Trigger

A download for the same target is already running.

## Outcome

The running download continues alone.
