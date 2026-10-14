---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator deletes a show, ticking Also delete hardlinked files from disk
  kind: actor
  actor: administrator
  entities:
  - {entity: show, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
- text: The Product deletes the show's files from disk, removes the show with its episodes, and prunes the emptied folders
  kind: product
  actor: administrator
  entities:
  - {entity: show, effect: removes, from: Returning}
  - {entity: episode, effect: removes, from: Downloaded, with: show}
  contexts:
    web:
      place: web::household::title
---

# Remove a show and its files

## Trigger

An administrator wants the space back as well.

## Outcome

The show and its files are gone.
