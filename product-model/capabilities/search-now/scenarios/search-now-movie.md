---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator chooses Search now on a wanted movie
  kind: actor
  actor: administrator
  entities:
  - {entity: movie, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
- text: The Product resets the movie's search attempts, searches with each of its search titles and grabs the best release the quality profile allows
  kind: product
  actor: administrator
  entities:
  - {entity: movie, effect: changes, from: Wanted, to: Downloading, facts: [Search attempts]}
  - {entity: grab, effect: creates, to: Downloading, facts: [Release title, Indexer, Grabbed, AI pick]}
  - {entity: quality-profile, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
---

# Search now for a movie

## Trigger

An administrator wants the movie now rather than at the next scheduled search.

## Outcome

The best release is downloading, marked when the language model picked it.

## Decision points

### Who picks the release

Is an AI provider configured for searches, and does more than one release pass the profile?

- Yes → The language model picks among the ten best-scored releases with seeders, and its pick is used only if it is one of them
- No, or the model fails, times out or is over its daily budget → The classic scorer's best release is grabbed
