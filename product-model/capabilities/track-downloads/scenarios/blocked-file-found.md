---
kind: edge
routes:
  web: Web
steps:
- text: The Product finds a file with a blocked extension inside a downloading torrent
  kind: condition
  unattended: true
  entities:
  - {entity: library-settings, effect: reads, facts: [Blocked file types]}
  contexts:
    web:
      place: web::household::title
- text: 'The Product rejects the release: fails the grab, blocklists it as a blocked file, removes the torrent and makes the movie wanted again'
  kind: product
  entities:
  - {entity: grab, effect: changes, from: Downloading, to: Failed, facts: [Failure reason, Released from client]}
  - {entity: blocklisted-release, effect: creates, facts: [Release title, Indexer, Reason, Kind, Blocked]}
  - {entity: movie, effect: changes, from: Downloading, to: Wanted, facts: []}
  contexts:
    web:
      place: web::household::title
---

# A download contains a blocked file type

## Trigger

A release carries an executable or script.

## Outcome

The release never reaches the library and is never grabbed again.
