---
kind: validation
routes:
  web: Web
steps:
- text: The Administrator grabs a release larger than the free space allows
  kind: actor
  actor: administrator
  entities:
  - {entity: grab, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
- text: The Product refuses because the grab would leave less than the minimum free space
  kind: condition
  entities:
  - {entity: library-settings, effect: reads, facts: [Minimum free space]}
  - {entity: grab, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
---

# Refuse when the download volume is nearly full

## Trigger

The download volume is short of space.

## Outcome

Nothing is grabbed.
