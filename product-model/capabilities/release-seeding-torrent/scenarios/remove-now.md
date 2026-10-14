---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator chooses Remove now on a seeding torrent and confirms
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::administration::downloads
- text: The Product removes the torrent and its downloaded files from the client, keeping the library copy, and records why and how much space was freed
  kind: product
  actor: administrator
  entities:
  - {entity: grab, effect: changes, facts: [Released from client, Freed size]}
  contexts:
    web:
      place: web::administration::downloads
---

# Remove a torrent now

## Trigger

An administrator needs the space or the torrent is not uploading.

## Outcome

The torrent is gone from the client; the library copy stays.

## Decision points

### Private tracker

Does a private tracker still expect seeding for it?

- Yes → The administrator is warned that removing it now can count against them on that tracker before confirming
- No → The torrent is removed on confirmation
