---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator enters Prowlarr's address and key and picks the indexers whose feeds are polled
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::administration::integrations
- text: The Product saves the connection and its feed indexers
  kind: product
  actor: administrator
  entities:
  - {entity: integration-settings, effect: changes, facts: [Prowlarr]}
  contexts:
    web:
      place: web::administration::integrations
---

# Connect an indexer manager

## Trigger

The instance needs somewhere to search releases.

## Outcome

Searches and RSS can use Prowlarr once it is the active indexer manager.
