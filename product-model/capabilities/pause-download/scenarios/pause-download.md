---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator chooses Pause download in a title's Download history
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::household::title
- text: The Product pauses the torrent in the download client
  kind: product
  actor: administrator
  entities:
  - {entity: grab, effect: reads, facts: [Release title]}
  contexts:
    web:
      place: web::household::title
---

# Pause a download

## Trigger

Bandwidth is needed elsewhere.

## Outcome

The download is listed as paused until it is resumed.
