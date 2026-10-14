---
kind: primary
routes:
  web: Web
steps:
- text: The Member chooses Not interested on the top card
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::household::for-you
- text: The Product records the title as not interested for that person and deals the next card
  kind: product
  actor: member
  entities:
  - {entity: dismissed-title, effect: creates, facts: [Catalog identity, Kind, Dismissed]}
  contexts:
    web:
      place: web::household::for-you
---

# Mark a title not interested

## Trigger

A suggestion does not appeal.

## Outcome

The title no longer appears in that person's deck.
