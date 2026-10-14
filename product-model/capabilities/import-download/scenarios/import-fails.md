---
kind: edge
routes:
  web: Web
steps:
- text: The Product cannot place a completed download, for example because its path is not visible to Rawkoon
  kind: condition
  unattended: true
  entities:
  - {entity: grab, effect: reads, facts: [Release title]}
  contexts:
    web:
      place: web::household::title
- text: The Product records the import error and notifies everyone who administers the instance
  kind: product
  entities:
  - {entity: grab, effect: changes, from: Completed, to: Import failed, facts: [Import error]}
  - {entity: notification, effect: creates, to: Unread, facts: [Title, Body, Kind, Link, Image, Received]}
  contexts:
    web:
      place: web::household::title
---

# An import fails

## Trigger

Something outside the release blocks the import.

## Outcome

The Library attention panel offers Retry ingest once the cause is fixed.
