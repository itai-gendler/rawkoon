---
kind: primary
routes:
  web: Web
steps:
- text: The Member chooses Watchlist on a title
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::household::browse
- text: The Product adds the title to that person's watchlist, keeping a movie's release date
  kind: product
  actor: member
  entities:
  - {entity: watchlist-item, effect: creates, facts: [Title, Kind, Poster, Overview, Year, Rating, Release date, Added]}
  - {entity: movie, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::browse
---

# Add a title to the watchlist

## Trigger

A person wants to remember a title.

## Outcome

The title is on their Watchlist page.

## Edge cases

- Adding a title already on the watchlist keeps one entry.
- The same control is on For You cards and on library title pages.
