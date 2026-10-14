---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator chooses Grab episode on a skipped episode
  kind: actor
  actor: administrator
  entities:
  - {entity: episode, effect: reads, facts: []}
  - {entity: grab, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
- text: The Product makes the episode wanted again, resets its attempts, searches for it and grabs the best release
  kind: product
  actor: administrator
  entities:
  - {entity: episode, effect: changes, from: Skipped, to: Downloading, facts: [Search attempts]}
  - {entity: grab, effect: creates, to: Downloading, facts: [Release title, Indexer, Grabbed]}
  contexts:
    web:
      place: web::household::title
---

# Grab a skipped episode

## Trigger

Automatic searching gave up on an episode.

## Outcome

The episode is downloading.
