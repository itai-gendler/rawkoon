---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator grabs an episode's release
  kind: actor
  actor: administrator
  entities:
  - {entity: episode, effect: reads, facts: []}
  - {entity: grab, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
- text: The Product links the release to the episode its name carries, adds it to the download client and marks the episode downloading
  kind: product
  actor: administrator
  entities:
  - {entity: grab, effect: creates, to: Downloading, facts: [Release title, Indexer, Grabbed]}
  - {entity: episode, effect: changes, from: Wanted, to: Downloading, facts: [Search attempts]}
  contexts:
    web:
      place: web::household::title
---

# Grab a release for an episode

## Trigger

An episode is missing.

## Outcome

The episode is downloading.

## Edge cases

- A release named for a different episode is linked to that episode; one naming an episode the show does not have is refused.
