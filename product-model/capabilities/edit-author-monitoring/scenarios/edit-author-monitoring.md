---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator picks the editions to add and the languages for an author
  kind: actor
  actor: administrator
  entities:
  - {entity: author, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::authors
- text: The Product saves them for the author's next check
  kind: product
  actor: administrator
  entities:
  - {entity: author, effect: changes, facts: [Editions to add, Languages]}
  contexts:
    web:
      place: web::household::authors
---

# Choose editions and languages

## Trigger

Only some editions or languages are wanted.

## Outcome

New titles arrive only in those languages, as those editions.
