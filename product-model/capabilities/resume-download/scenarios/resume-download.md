---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator chooses Resume download
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::household::title
- text: The Product resumes the torrent in the download client
  kind: product
  actor: administrator
  entities:
  - {entity: grab, effect: reads, facts: [Release title]}
  contexts:
    web:
      place: web::household::title
---

# Resume a download

## Trigger

A paused download should continue.

## Outcome

The download is transferring again.
