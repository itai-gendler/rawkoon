---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator chooses Grab on a release in a movie's search results
  kind: actor
  actor: administrator
  entities:
  - {entity: movie, effect: reads, facts: []}
  - {entity: grab, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
- text: The Product adds the torrent to the active download client with Rawkoon's label, records the grab, marks the movie downloading and notifies everyone who administers the instance
  kind: product
  actor: administrator
  entities:
  - {entity: grab, effect: creates, to: Downloading, facts: [Release title, Indexer, Grabbed, Upgrade]}
  - {entity: movie, effect: changes, from: Wanted, to: Downloading, facts: [Search attempts]}
  - {entity: notification, effect: creates, to: Unread, facts: [Title, Body, Kind, Link, Image, Received]}
  contexts:
    web:
      place: web::household::title
---

# Grab a release for a movie

## Trigger

An administrator picked a release.

## Outcome

The release is downloading and listed in the movie's Download history.
