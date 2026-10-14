---
kind: validation
routes:
  web: Web
steps:
- text: The Member opens an audiobook whose chapter files are not registered
  kind: actor
  actor: member
  entities:
  - {entity: audiobook, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::book
- text: The Product does not offer Listen and explains the audiobook is not ready
  kind: condition
  entities:
  - {entity: audiobook, effect: reads, facts: [Chapters]}
  contexts:
    web:
      place: web::household::book
---

# An audiobook without chapters is not playable

## Trigger

The audiobook has no chapters yet.

## Outcome

The person cannot play it until its chapters exist.
