---
kind: primary
routes:
  web: Web
steps:
- text: The Product finds a season pack's torrent finished for a show the catalog lists as ended
  kind: condition
  unattended: true
  entities:
  - {entity: show, effect: reads, facts: [Series status]}
  contexts:
    web:
      place: web::household::title
- text: The Product marks the grab completed and the show downloaded, and queues the import
  kind: product
  entities:
  - {entity: grab, effect: changes, from: Downloading, to: Completed, facts: [Completed]}
  - {entity: show, effect: changes, from: Downloading, to: Downloaded, facts: []}
  contexts:
    web:
      place: web::household::title
---

# A season pack completes for an ended show

## Trigger

A pack finishes for a series that has ended.

## Outcome

The show is downloaded.
