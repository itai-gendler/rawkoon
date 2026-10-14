---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator chooses Block on a release in the search results
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::household::title
- text: The Product adds the release to the blocklist
  kind: product
  actor: administrator
  entities:
  - {entity: blocklisted-release, effect: creates, facts: [Release title, Indexer, Reason, Kind, Blocked]}
  contexts:
    web:
      place: web::household::title
---

# Block a release

## Trigger

A release is fake, mislabeled or unwanted.

## Outcome

The release is never grabbed, by hand or automatically.
