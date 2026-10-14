---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator chooses Grab on a release for an audiobook
  kind: actor
  actor: administrator
  entities:
  - {entity: audiobook, effect: reads, facts: []}
  - {entity: grab, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::book
- text: The Product adds the release to the download client and marks the audiobook downloading
  kind: product
  actor: administrator
  entities:
  - {entity: grab, effect: creates, to: Downloading, facts: [Release title, Indexer, Grabbed]}
  - {entity: audiobook, effect: changes, from: Wanted, to: Downloading, facts: [Search attempts]}
  contexts:
    web:
      place: web::household::book
---

# Grab a release for a book edition

## Trigger

An administrator picked a book release.

## Outcome

The edition is downloading; it appears in the library once the download finishes and is imported.
