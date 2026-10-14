---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator chooses Browse torrents for this season
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::household::title
- text: The Product searches for the season and marks season packs and complete-series releases
  kind: product
  actor: administrator
  entities:
  - {entity: show, effect: reads, facts: [Search title, Quality profile]}
  contexts:
    web:
      place: web::household::title
---

# Search releases for a season

## Trigger

An administrator wants a whole season at once.

## Outcome

The administrator sees season packs and single episodes for the season.
