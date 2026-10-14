---
kind: edge
routes:
  web: Web
steps:
- text: The Product finds a torrent in an error state, or past the maximum age without finishing
  kind: condition
  unattended: true
  entities:
  - {entity: library-settings, effect: reads, facts: [Download checks]}
  contexts:
    web:
      place: web::household::title
- text: The Product fails the grab, makes the movie wanted again and notifies everyone who administers the instance
  kind: product
  entities:
  - {entity: grab, effect: changes, from: Downloading, to: Failed, facts: [Failure reason]}
  - {entity: movie, effect: changes, from: Downloading, to: Wanted, facts: []}
  - {entity: notification, effect: creates, to: Unread, facts: [Title, Body, Kind, Link, Image, Received]}
  contexts:
    web:
      place: web::household::title
---

# The client reports an error or the download is too old

## Trigger

The download cannot finish.

## Outcome

The movie is wanted again.
