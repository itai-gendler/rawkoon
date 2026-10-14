---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator chooses Add to Library on a movie
  kind: actor
  actor: administrator
  entities:
  - {entity: movie, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::browse
- text: The Product adds the movie as wanted and monitored, with the default movie profile and its digital release date for the instance's country
  kind: product
  actor: administrator
  entities:
  - {entity: library-settings, effect: reads, facts: [Default movie profile]}
  - {entity: movie, effect: creates, to: Wanted, facts: [Title, Sort title, Year, Overview, Poster, Catalog identity, Monitored, Quality profile, Search title, Digital release date, Added]}
  contexts:
    web:
      place: web::household::browse
---

# Add a movie

## Trigger

An administrator wants a movie in the library.

## Outcome

The movie is in the library, wanted; scheduled searches look for it once it is released digitally.

## Edge cases

- The same control is on Home's featured titles, the For You deck and the Calendar.
