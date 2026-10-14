---
kind: primary
routes:
  web: Web
steps:
- text: The Member opens a movie or show from the library
  kind: actor
  actor: member
  entities:
  - {entity: movie, effect: reads, facts: []}
  - {entity: show, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::library
- text: The Product presents the title's details, its seasons and episodes, and its files
  kind: product
  actor: member
  entities:
  - {entity: show, effect: reads, facts: [Title, Year, Overview, Poster, Backdrop, Seasons]}
  - {entity: episode, effect: reads, facts: [Season, Number, Title, Air date]}
  - {entity: video-file, effect: reads, facts: [Resolution, Source, Size]}
  contexts:
    web:
      place: web::household::title
---

# Open a title

## Trigger

A person wants to know more about a title.

## Outcome

The person is on the title's page; administrators also get its search and management controls.
