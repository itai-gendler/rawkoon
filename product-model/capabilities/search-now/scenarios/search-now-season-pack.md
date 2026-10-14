---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator chooses Auto-grab season pack
  kind: actor
  actor: administrator
  entities:
  - {entity: grab, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
- text: The Product makes the season's skipped episodes wanted again, searches for the season and grabs the best pack
  kind: product
  actor: administrator
  entities:
  - {entity: episode, effect: changes, from: Skipped, to: Wanted, facts: [Search attempts]}
  - {entity: grab, effect: creates, to: Downloading, facts: [Release title, Indexer, Grabbed, Season]}
  - {entity: show, effect: changes, from: Wanted, to: Downloading, facts: []}
  contexts:
    web:
      place: web::household::title
---

# Auto-grab a season pack

## Trigger

A season is missing.

## Outcome

The season pack is downloading.

## Edge cases

- When no pack is found the episodes are left to be searched one by one.
- A season with an episode already downloading is refused.
