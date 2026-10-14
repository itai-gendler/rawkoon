---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator grabs a better release for a downloaded movie in upgrade mode
  kind: actor
  actor: administrator
  entities:
  - {entity: movie, effect: reads, facts: []}
  - {entity: grab, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
- text: The Product records the grab as an upgrade and marks the movie upgrading, keeping its current file in place
  kind: product
  actor: administrator
  entities:
  - {entity: grab, effect: creates, to: Downloading, facts: [Release title, Indexer, Grabbed, Upgrade]}
  - {entity: movie, effect: changes, from: Downloaded, to: Upgrading, facts: [Search attempts]}
  contexts:
    web:
      place: web::household::title
---

# Grab an upgrade

## Trigger

A better release exists for a title already in the library.

## Outcome

The upgrade is downloading; the current file stays until the new one is imported.
