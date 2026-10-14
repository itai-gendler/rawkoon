---
kind: primary
routes:
  web: Web
steps:
- text: Every fifteen minutes, with automatic release on, the Product finds a torrent that reached its seed ratio or time
  kind: condition
  unattended: true
  entities:
  - {entity: library-settings, effect: reads, facts: [Automatic seeding release, Seed targets]}
  - {entity: grab, effect: reads, facts: [Indexer]}
  contexts:
    web:
      place: web::administration::downloads
- text: The Product removes the torrent from the client and records the release
  kind: product
  entities:
  - {entity: grab, effect: changes, facts: [Released from client, Freed size]}
  contexts:
    web:
      place: web::administration::downloads
---

# Remove a torrent that met its target

## Trigger

A torrent finished its seeding duty.

## Outcome

The torrent is gone from the client; the Downloads page counts the space freed.

## Edge cases

- Automatic release is off until an administrator turns it on.
- With the move file operation, finished torrents are released without waiting for a target, since nothing is left to seed.
