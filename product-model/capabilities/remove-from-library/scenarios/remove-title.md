---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator chooses Delete media on a movie and confirms
  kind: actor
  actor: administrator
  entities:
  - {entity: movie, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
- text: The Product removes the movie and its file records, keeps its finished grabs seeding to target and abandons any grab still downloading
  kind: product
  actor: administrator
  entities:
  - {entity: movie, effect: removes, from: Downloaded}
  - {entity: video-file, effect: removes, with: movie}
  - {entity: grab, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
---

# Remove a movie

## Trigger

An administrator no longer wants a title.

## Outcome

The movie is gone from the library; its files stay on disk.

## Decision points

### Seeding torrents

Do the title's torrents still owe seeding?

- Keep seeding until the target is met → Rawkoon removes them from the client later, once each meets its target
- Remove the torrent now → Rawkoon removes the torrents it owns from the client at once, except one another title still owns
