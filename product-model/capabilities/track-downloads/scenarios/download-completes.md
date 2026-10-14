---
kind: primary
routes:
  web: Web
steps:
- text: The Product finds a grab's torrent finished in the download client
  kind: condition
  unattended: true
  entities:
  - {entity: grab, effect: reads, facts: [Release title]}
  contexts:
    web:
      place: web::household::title
- text: The Product marks the grab completed and the movie downloaded, and queues the import
  kind: product
  entities:
  - {entity: grab, effect: changes, from: Downloading, to: Completed, facts: [Completed]}
  - {entity: movie, effect: changes, from: Downloading, to: Downloaded, facts: [Search attempts]}
  contexts:
    web:
      place: web::household::title
- text: The Product marks the approved request for the movie available and notifies the requester
  kind: product
  entities:
  - {entity: request, effect: changes, from: Approved, to: Available, facts: []}
  - {entity: notification, effect: creates, to: Unread, facts: [Title, Body, Kind, Link, Image, Received]}
  - {entity: movie, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
---

# A download completes

## Trigger

A download finishes in the client.

## Outcome

The title is downloaded, the requester is told it is available, and the import is queued.

## Edge cases

- A finished season pack for a series still airing leaves the show returning rather than downloaded.
- A finished upgrade returns the title from upgrading to downloaded.
