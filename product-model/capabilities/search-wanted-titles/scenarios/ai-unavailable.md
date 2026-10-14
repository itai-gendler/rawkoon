---
kind: edge
routes:
  web: Web
steps:
- text: The Product asks the language model to pick a release and gets no usable answer within thirty seconds
  kind: condition
  unattended: true
  entities:
  - {entity: integration-settings, effect: reads, facts: [AI provider]}
  contexts:
    web:
      place: web::household::title
- text: The Product grabs the classic scorer's choice instead
  kind: product
  entities:
  - {entity: grab, effect: creates, to: Downloading, facts: [Release title, Indexer, Grabbed]}
  - {entity: movie, effect: changes, from: Wanted, to: Downloading, facts: []}
  contexts:
    web:
      place: web::household::title
---

# The language model is unavailable

## Trigger

The model fails, times out, is rate-limited, picks a release it was not offered, or the daily budget is spent.

## Outcome

The grab happens as if no model were configured.
