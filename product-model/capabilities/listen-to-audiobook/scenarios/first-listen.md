---
kind: primary
routes:
  web: Web
steps:
- text: The Member chooses Listen on an audiobook they have not started
  kind: actor
  actor: member
  entities:
  - {entity: audiobook, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::book
- text: The Product starts at the beginning and keeps a listening position for the person
  kind: product
  actor: member
  entities:
  - {entity: listening-progress, effect: creates, facts: [Position, Book length, Finished, Updated, Device]}
  contexts:
    web:
      place: web::household::listen
---

# Start an audiobook

## Trigger

A person starts a new audiobook.

## Outcome

The person's position is kept from the first minute.
