---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator chooses Remove download and confirms, optionally deleting downloaded files
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::household::title
- text: The Product removes the torrent from the client, deletes the grab and, with no other download running, makes the movie wanted again
  kind: product
  actor: administrator
  entities:
  - {entity: grab, effect: removes, from: Downloading}
  - {entity: movie, effect: changes, from: Downloading, to: Wanted, facts: []}
  contexts:
    web:
      place: web::household::title
---

# Remove a running download

## Trigger

A download is wrong or stuck.

## Outcome

The download is gone and the movie can be grabbed again.

## Edge cases

- Removing an upgrade's download leaves the title downloaded with its current file.
