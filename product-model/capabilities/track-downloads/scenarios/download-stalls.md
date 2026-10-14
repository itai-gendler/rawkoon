---
kind: edge
routes:
  web: Web
steps:
- text: The Product finds a torrent that made no progress for longer than the stall timeout
  kind: condition
  unattended: true
  entities:
  - {entity: library-settings, effect: reads, facts: [Download checks]}
  contexts:
    web:
      place: web::household::title
- text: The Product fails the grab, blocklists the release as stalled, removes the torrent if Rawkoon added it, makes the movie wanted again and notifies everyone who administers the instance
  kind: product
  entities:
  - {entity: grab, effect: changes, from: Downloading, to: Failed, facts: [Failure reason, Released from client]}
  - {entity: blocklisted-release, effect: creates, facts: [Release title, Indexer, Reason, Kind, Blocked]}
  - {entity: movie, effect: changes, from: Downloading, to: Wanted, facts: []}
  - {entity: notification, effect: creates, to: Unread, facts: [Title, Body, Kind, Link, Image, Received]}
  contexts:
    web:
      place: web::household::title
---

# A download stalls

## Trigger

A release has no seeders.

## Outcome

The movie is wanted again and the next search will not pick that release.
