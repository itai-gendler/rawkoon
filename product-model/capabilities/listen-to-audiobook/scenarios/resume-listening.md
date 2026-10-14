---
kind: primary
routes:
  web: Web
  iphone: iPhone
steps:
- text: The Member chooses Listen on an audiobook with chapter files
  kind: actor
  actor: member
  entities:
  - {entity: audiobook, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::book
    iphone:
      place: iphone::household::book
- text: The Product opens the player at the person's saved position on the whole-book timeline
  kind: product
  actor: member
  entities:
  - {entity: audiobook, effect: reads, facts: [Chapters, Duration]}
  - {entity: listening-progress, effect: reads, facts: [Position]}
  - {entity: book, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::listen
    iphone:
      place: iphone::household::player
- text: The Member listens
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::household::listen
    iphone:
      place: iphone::household::player
- text: The Product records the new position as the person listens
  kind: product
  actor: member
  entities:
  - {entity: listening-progress, effect: changes, facts: [Position, Book length, Finished, Updated, Device]}
  contexts:
    web:
      place: web::household::listen
    iphone:
      place: iphone::household::player
---

# Resume listening

## Trigger

A person wants to continue an audiobook.

## Outcome

The person picks up where they stopped, on whichever device.

## Edge cases

- The web player plays only while its tab is in the foreground.
- The iPhone keeps playing with the screen locked and offers Now Playing controls.
