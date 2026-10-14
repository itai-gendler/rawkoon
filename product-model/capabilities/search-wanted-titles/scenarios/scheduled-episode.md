---
kind: primary
routes:
  web: Web
steps:
- text: The Product finds a monitored wanted episode whose air date has passed
  kind: condition
  unattended: true
  entities:
  - {entity: episode, effect: reads, facts: [Air date, Monitored]}
  contexts:
    web:
      place: web::household::title
- text: The Product searches for the episode and grabs the best release
  kind: product
  entities:
  - {entity: grab, effect: creates, to: Downloading, facts: [Release title, Indexer, Grabbed]}
  - {entity: episode, effect: changes, from: Wanted, to: Downloading, facts: [Search attempts]}
  contexts:
    web:
      place: web::household::title
---

# Grab an aired episode

## Trigger

An episode aired.

## Outcome

The episode is downloading.
