---
kind: primary
routes:
  web: Web
steps:
- text: The Product finds a title by a monitored author published on or after the monitoring date, in one of the author's chosen languages, that the library lacks
  kind: condition
  unattended: true
  entities:
  - {entity: general-settings, effect: reads, facts: [Books]}
  - {entity: author, effect: reads, facts: [Monitored, Monitored from, Languages, Editions to add]}
  contexts:
    web:
      place: web::household::authors
- text: The Product adds the book with the chosen editions and the author's quality profile, records the check and notifies everyone who administers the instance
  kind: product
  entities:
  - {entity: book, effect: creates, facts: [Title, Authors, Language, Published, Catalog identity, Added]}
  - {entity: ebook, effect: creates, to: Wanted, facts: [Monitored, Quality profile], with: book}
  - {entity: author, effect: changes, facts: [Last checked]}
  - {entity: notification, effect: creates, to: Unread, facts: [Title, Body, Kind, Link, Image, Received]}
  - {entity: quality-profile, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::authors
---

# Add a new title by a followed author

## Trigger

A followed author publishes something new.

## Outcome

The new title is wanted and will be searched for.
