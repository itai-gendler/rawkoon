---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator grabs a better season pack for a downloaded show in upgrade mode
  kind: actor
  actor: administrator
  entities:
  - {entity: show, effect: reads, facts: []}
  - {entity: grab, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
- text: The Product records the grab as an upgrade and marks the show upgrading, keeping its current files
  kind: product
  actor: administrator
  entities:
  - {entity: grab, effect: creates, to: Downloading, facts: [Release title, Indexer, Grabbed, Season, Upgrade]}
  - {entity: show, effect: changes, from: Downloaded, to: Upgrading, facts: []}
  contexts:
    web:
      place: web::household::title
---

# Grab a season pack as an upgrade

## Trigger

A better pack exists for a season already in the library.

## Outcome

The upgrade is downloading.
