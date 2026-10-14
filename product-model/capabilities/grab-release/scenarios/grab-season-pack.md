---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator grabs a season pack
  kind: actor
  actor: administrator
  entities:
  - {entity: grab, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
- text: The Product records a grab for the season, adds it to the download client and marks the show downloading
  kind: product
  actor: administrator
  entities:
  - {entity: grab, effect: creates, to: Downloading, facts: [Release title, Indexer, Grabbed, Season]}
  - {entity: show, effect: changes, from: Wanted, to: Downloading, facts: []}
  contexts:
    web:
      place: web::household::title
---

# Grab a season pack

## Trigger

A whole season is wanted.

## Outcome

The season pack is downloading.
