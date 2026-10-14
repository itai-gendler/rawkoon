---
kind: primary
routes:
  web: Web
steps:
- text: With books on, the Product finds a monitored wanted ebook
  kind: condition
  unattended: true
  entities:
  - {entity: general-settings, effect: reads, facts: [Books]}
  - {entity: ebook, effect: reads, facts: [Monitored]}
  - {entity: book, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::book
- text: The Product searches for it and grabs the best release its profile allows
  kind: product
  entities:
  - {entity: grab, effect: creates, to: Downloading, facts: [Release title, Indexer, Grabbed]}
  - {entity: ebook, effect: changes, from: Wanted, to: Downloading, facts: [Search attempts]}
  contexts:
    web:
      place: web::household::book
---

# Grab a wanted edition

## Trigger

A wanted edition has not been found yet.

## Outcome

The edition is downloading.

## Edge cases

- Books have no release-date gate.
