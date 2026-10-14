---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator chooses to search automatically for a skipped audiobook
  kind: actor
  actor: administrator
  entities:
  - {entity: audiobook, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::book
- text: The Product clears the skip, searches for the edition and grabs the best release its profile allows
  kind: product
  actor: administrator
  entities:
  - {entity: audiobook, effect: changes, from: Skipped, to: Downloading, facts: [Search attempts]}
  - {entity: grab, effect: creates, to: Downloading, facts: [Release title, Indexer, Grabbed]}
  contexts:
    web:
      place: web::household::book
---

# Search now for a skipped audiobook

## Trigger

Automatic searching gave up on an edition.

## Outcome

The edition is downloading.
