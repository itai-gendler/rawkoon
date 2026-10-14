---
kind: edge
routes:
  web: Web
steps:
- text: The Product finds no usable video file in a completed download
  kind: condition
  unattended: true
  entities:
  - {entity: grab, effect: reads, facts: [Release title]}
  - {entity: video-file, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
- text: 'The Product rejects the release: fails the grab, blocklists it as import rejected, removes the torrent and makes the movie wanted again'
  kind: product
  entities:
  - {entity: grab, effect: changes, from: Completed, to: Failed, facts: [Import error, Failure reason]}
  - {entity: blocklisted-release, effect: creates, facts: [Release title, Indexer, Reason, Kind, Blocked]}
  - {entity: movie, effect: changes, from: Downloaded, to: Wanted, facts: []}
  - {entity: notification, effect: creates, to: Unread, facts: [Title, Body, Kind, Link, Image, Received]}
  contexts:
    web:
      place: web::household::title
---

# Reject a download with no usable content

## Trigger

The release was not what it claimed.

## Outcome

The movie is wanted again and the release is never grabbed again.
