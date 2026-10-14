---
kind: primary
routes:
  web: Web
steps:
- text: The Member chooses Undo last action right after marking a title not interested
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::household::for-you
- text: The Product forgets the title as not interested and puts its card back on top
  kind: product
  actor: member
  entities:
  - {entity: dismissed-title, effect: removes}
  contexts:
    web:
      place: web::household::for-you
---

# Undo the last Not interested

## Trigger

A person dismissed a card by mistake.

## Outcome

The card is back in the deck.
