---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator deletes a movie's file, choosing to delete it on disk too
  kind: actor
  actor: administrator
  entities:
  - {entity: movie, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
- text: The Product removes the record, deletes the file from disk and, with no file left, makes the movie wanted again
  kind: product
  actor: administrator
  entities:
  - {entity: video-file, effect: removes}
  - {entity: movie, effect: changes, from: Downloaded, to: Wanted, facts: [Search attempts]}
  contexts:
    web:
      place: web::household::title
---

# Delete a movie's file

## Trigger

A file is bad or unwanted.

## Outcome

The file is gone and the movie is searched for again.
