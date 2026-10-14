---
kind: primary
routes:
  web: Web
steps:
- text: The Product finds an episode's torrent finished
  kind: condition
  unattended: true
  entities:
  - {entity: grab, effect: reads, facts: [Release title]}
  - {entity: episode, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
- text: The Product marks the grab completed and the episode downloaded, and queues the import
  kind: product
  entities:
  - {entity: grab, effect: changes, from: Downloading, to: Completed, facts: [Completed]}
  - {entity: episode, effect: changes, from: Downloading, to: Downloaded, facts: [Downloaded, Search attempts]}
  contexts:
    web:
      place: web::household::title
---

# An episode download completes

## Trigger

An episode finishes downloading.

## Outcome

The episode is downloaded.
