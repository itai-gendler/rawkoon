---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator picks qBittorrent, Transmission or Deluge, enters its address, credentials, label and save path, and tests the connection
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::administration::integrations
- text: The Product checks the client answers and saves the connection, keeping secrets encrypted
  kind: product
  actor: administrator
  entities:
  - {entity: integration-settings, effect: changes, facts: [Download client]}
  contexts:
    web:
      place: web::administration::integrations
---

# Connect the download client

## Trigger

The instance needs a client to download with.

## Outcome

Grabs go to that client.
