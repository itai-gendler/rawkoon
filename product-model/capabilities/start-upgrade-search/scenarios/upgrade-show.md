---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator chooses Auto Search for a show
  kind: actor
  actor: administrator
  entities:
  - {entity: show, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
- text: The Product marks only the downloaded episodes whose files fail the profile upgrading and queues a search for each
  kind: product
  actor: administrator
  entities:
  - {entity: episode, effect: changes, from: Downloaded, to: Upgrading, facts: []}
  contexts:
    web:
      place: web::household::title
---

# Upgrade a show's failing episodes

## Trigger

Some of a show's episodes fail its new profile.

## Outcome

Each failing episode is searched for an upgrade.

## Edge cases

- A show with no profile has every downloaded episode searched.
