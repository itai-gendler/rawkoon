---
kind: primary
routes:
  web: Web
steps:
- text: The Product finds episodes on TMDB that the show does not have yet
  kind: condition
  unattended: true
  entities:
  - {entity: show, effect: reads, facts: [Catalog identity]}
  - {entity: episode, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
- text: The Product adds them as wanted and monitored and refreshes the show's series status
  kind: product
  entities:
  - {entity: episode, effect: creates, to: Wanted, facts: [Season, Number, Title, Air date, Monitored]}
  - {entity: show, effect: changes, facts: [Series status, Episodes, Seasons]}
  contexts:
    web:
      place: web::household::title
---

# Add newly announced episodes

## Trigger

A show announces new episodes.

## Outcome

The episodes are wanted and will be searched for once aired.
