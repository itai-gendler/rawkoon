---
kind: edge
routes:
  web: Web
steps:
- text: The Administrator rescans a movie whose file was deleted outside Rawkoon
  kind: actor
  actor: administrator
  entities:
  - {entity: movie, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
- text: The Product drops the record and makes the movie wanted again
  kind: product
  actor: administrator
  entities:
  - {entity: video-file, effect: removes}
  - {entity: movie, effect: changes, from: Downloaded, to: Wanted, facts: [Search attempts]}
  contexts:
    web:
      place: web::household::title
---

# A rescan finds no file left

## Trigger

The movie's file is gone from disk.

## Outcome

The movie is wanted and will be searched for again.
