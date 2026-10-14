---
kind: primary
routes:
  web: Web
steps:
- text: The Product finds allowed releases for a wanted movie whose profile has a grab delay, none of them past it
  kind: condition
  unattended: true
  entities:
  - {entity: quality-profile, effect: reads, facts: [Grab delay, Skip delay at cutoff]}
  - {entity: movie, effect: reads, facts: []}
  - {entity: grab, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
- text: The Product holds the candidates until the delay ends
  kind: product
  entities:
  - {entity: pending-release, as: held, effect: creates, facts: [Release title, Indexer, Score, Grab after]}
  contexts:
    web:
      place: web::household::title
- text: Once the delay ends, the Product grabs the best held release and drops the rest
  kind: product
  entities:
  - {entity: grab, effect: creates, to: Downloading, facts: [Release title, Indexer, Grabbed]}
  - {entity: movie, effect: changes, from: Wanted, to: Downloading, facts: []}
  - {entity: pending-release, as: held, effect: removes}
  contexts:
    web:
      place: web::household::title
---

# Hold a release for the grab delay

## Trigger

The profile waits for better releases after publication.

## Outcome

The best release seen during the delay is grabbed.

## Edge cases

- A release that already meets the resolution cutoff skips the wait when the profile says so.
- Manual and upgrade searches are never delayed.
