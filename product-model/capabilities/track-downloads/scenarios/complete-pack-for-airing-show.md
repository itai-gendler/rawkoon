---
kind: primary
routes:
  web: Web
steps:
- text: The Product finds a season pack's torrent finished for a show the catalog lists as returning
  kind: condition
  unattended: true
  entities:
  - {entity: show, effect: reads, facts: [Series status]}
  contexts:
    web:
      place: web::household::title
- text: The Product marks the grab completed and the show returning, and queues the import
  kind: product
  entities:
  - {entity: grab, effect: changes, from: Downloading, to: Completed, facts: [Completed]}
  - {entity: show, effect: changes, from: Downloading, to: Returning, facts: []}
  contexts:
    web:
      place: web::household::title
---

# A season pack completes for an airing show

## Trigger

A pack finishes for a series that is still running.

## Outcome

The show is returning until its run ends.
