---
kind: edge
routes:
  web: Web
steps:
- text: The Product finds at least two live downloads, and all of them, past the stall timeout in the same check
  kind: condition
  unattended: true
  entities:
  - {entity: library-settings, effect: reads, facts: [Download checks]}
  contexts:
    web:
      place: web::household::title
- text: The Product fails the grabs without blocklisting their releases and makes their titles wanted again
  kind: product
  entities:
  - {entity: grab, effect: changes, from: Downloading, to: Failed, facts: [Failure reason]}
  - {entity: movie, effect: changes, from: Downloading, to: Wanted, facts: []}
  contexts:
    web:
      place: web::household::title
---

# Every download stalls at once

## Trigger

The network or VPN dropped.

## Outcome

The releases stay eligible because the outage was not their fault.
