---
kind: edge
routes:
  web: Web
steps:
- text: The Administrator grabs a release qBittorrent already has
  kind: actor
  actor: administrator
  entities:
  - {entity: grab, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
- text: The Product attaches the existing torrent to the grab instead of adding it again, and never removes it from the client
  kind: product
  actor: administrator
  entities:
  - {entity: grab, effect: creates, to: Downloading, facts: [Release title, Indexer, Grabbed, Released from client]}
  - {entity: movie, effect: changes, from: Wanted, to: Downloading, facts: [Search attempts]}
  contexts:
    web:
      place: web::household::title
---

# Adopt a torrent already in the client

## Trigger

The household added the torrent by hand earlier.

## Outcome

Rawkoon follows the existing torrent; if it already finished, the grab completes at once.

## Edge cases

- With no download client configured the grab is refused.
