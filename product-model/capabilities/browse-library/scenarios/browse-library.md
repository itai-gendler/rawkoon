---
kind: primary
routes:
  web: Web
steps:
- text: The Member opens Library and filters by kind, status or audio language, searches by title or sorts
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::household::library
- text: The Product lists the matching movies and shows with their status
  kind: product
  actor: member
  entities:
  - {entity: movie, effect: reads, facts: [Title, Year, Poster, Added]}
  - {entity: show, effect: reads, facts: [Title, Year, Poster, Downloaded episodes, Episodes, Added]}
  contexts:
    web:
      place: web::household::library
---

# Browse the library

## Trigger

A person looks through what the household has.

## Outcome

The person sees the library with counts of movies and shows.
