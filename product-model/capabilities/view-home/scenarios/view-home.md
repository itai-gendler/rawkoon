---
kind: primary
routes:
  web: Web
steps:
- text: The Member opens Home
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::household::home
- text: The Product presents recently added movies and shows, upcoming releases, and the person's audiobooks and ebooks in progress to continue
  kind: product
  actor: member
  entities:
  - {entity: movie, effect: reads, facts: [Title, Poster, Added]}
  - {entity: show, effect: reads, facts: [Title, Poster, Added]}
  - {entity: listening-progress, effect: reads, facts: [Position, Finished]}
  - {entity: reading-progress, effect: reads, facts: [Offset, Finished]}
  - {entity: audiobook, effect: reads, facts: []}
  - {entity: ebook, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::home
---

# Open Home

## Trigger

A person signs in or returns to Home.

## Outcome

The person sees what is new and can pick up where they left off.

## Edge cases

- Administrators also see the Library attention panel and the download activity on Home.
