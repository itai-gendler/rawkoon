---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator chooses Delete episode and confirms
  kind: actor
  actor: administrator
  entities:
  - {entity: episode, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
- text: The Product deletes the episode's files from disk and makes the episode wanted again
  kind: product
  actor: administrator
  entities:
  - {entity: video-file, effect: removes}
  - {entity: episode, effect: changes, from: Downloaded, to: Wanted, facts: [Downloaded]}
  contexts:
    web:
      place: web::household::title
---

# Delete an episode's file

## Trigger

An episode's file should be replaced.

## Outcome

The episode is wanted again.
