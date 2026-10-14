---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator chooses Add to Library on a show
  kind: actor
  actor: administrator
  entities:
  - {entity: show, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::browse
- text: The Product adds the show and every episode TMDB lists, all wanted and monitored, with the default show profile
  kind: product
  actor: administrator
  entities:
  - {entity: library-settings, effect: reads, facts: [Default show profile]}
  - {entity: show, effect: creates, to: Wanted, facts: [Title, Sort title, Year, Overview, Poster, Catalog identity, Monitored, Quality profile, Search title, Series status, Added]}
  - {entity: episode, effect: creates, to: Wanted, facts: [Season, Number, Title, Air date, Monitored], with: show}
  contexts:
    web:
      place: web::household::browse
---

# Add a show

## Trigger

An administrator wants a show in the library.

## Outcome

The show and its episodes are wanted; aired episodes are searched for.
