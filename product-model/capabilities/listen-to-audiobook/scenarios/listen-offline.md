---
kind: primary
routes:
  iphone: iPhone
steps:
- text: The Member plays a downloaded audiobook with no connection
  kind: actor
  actor: member
  entities:
  - {entity: downloaded-audiobook, effect: reads, facts: []}
  contexts:
    iphone:
      place: iphone::household::player
- text: The Product plays the chapters from the phone and sends the saved position to the server on the next connection
  kind: product
  actor: member
  entities:
  - {entity: downloaded-audiobook, effect: reads, facts: [Chapters on device]}
  - {entity: listening-progress, effect: changes, facts: [Position, Updated, Device]}
  contexts:
    iphone:
      place: iphone::household::player
---

# Listen offline on iPhone

## Trigger

A person is on a plane.

## Outcome

Listening works offline and the position syncs afterwards.
