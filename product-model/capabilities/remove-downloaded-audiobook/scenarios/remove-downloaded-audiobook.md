---
kind: primary
routes:
  iphone: iPhone
steps:
- text: The Member chooses Remove Download and confirms
  kind: actor
  actor: member
  entities: []
  contexts:
    iphone:
      place: iphone::household::book
- text: The Product deletes the chapters from the phone
  kind: product
  actor: member
  entities:
  - {entity: downloaded-audiobook, effect: removes, from: Downloaded}
  contexts:
    iphone:
      place: iphone::household::book
---

# Remove a downloaded audiobook

## Trigger

A person needs the space on their phone.

## Outcome

The audiobook streams again instead of playing offline.
