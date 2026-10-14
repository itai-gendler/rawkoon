---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator chooses Auto Search in Upgrade Quality
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::household::title
- text: The Product marks the movie upgrading and queues a search for a release meeting its profile
  kind: product
  actor: administrator
  entities:
  - {entity: movie, effect: changes, from: Downloaded, to: Upgrading, facts: []}
  contexts:
    web:
      place: web::household::title
- text: The Product grabs the best upgrade the search finds as an upgrade
  kind: product
  actor: administrator
  entities:
  - {entity: grab, effect: creates, to: Downloading, facts: [Release title, Indexer, Grabbed, Upgrade]}
  contexts:
    web:
      place: web::household::title
---

# Upgrade a movie automatically

## Trigger

A movie's file fails its new profile.

## Outcome

An upgrade is downloading while the current file stays.

## Edge cases

- When no upgrade is found the movie goes back to downloaded with its current file.
