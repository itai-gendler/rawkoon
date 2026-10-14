---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator enters an OpenAI-compatible endpoint, model and key, prices and a daily budget, and picks where the model is asked
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::administration::integrations
- text: The Product saves the provider, keeping the key encrypted
  kind: product
  actor: administrator
  entities:
  - {entity: integration-settings, effect: changes, facts: [AI provider]}
  contexts:
    web:
      place: web::administration::integrations
---

# Connect an AI provider

## Trigger

The household wants a language model to choose between allowed releases.

## Outcome

Release picks consult the model where it is switched on.
