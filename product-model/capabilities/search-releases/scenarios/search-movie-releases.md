---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator opens the Search tab of a movie, optionally editing the query
  kind: actor
  actor: administrator
  entities:
  - {entity: movie, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
- text: The Product searches through the active indexer manager with the movie's search title and year and scores each release against the movie's quality profile
  kind: product
  actor: administrator
  entities:
  - {entity: movie, effect: reads, facts: [Search title, Year, Quality profile]}
  - {entity: quality-profile, effect: reads, facts: [Minimum resolution, Resolution cutoff, Preferred languages, Require HDR, Maximum size, Minimum seeders, Custom formats]}
  - {entity: library-settings, effect: reads, facts: [Active indexer manager]}
  contexts:
    web:
      place: web::household::title
- text: The Product lists the releases with size, seeders and score, and the rejected ones with the rules they fail
  kind: product
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::household::title
---

# Search releases for a movie

## Trigger

An administrator wants to choose the release by hand.

## Outcome

The administrator sees the candidates and can grab one or block one.
