---
kind: primary
routes:
  iphone: iPhone
steps:
- text: The Member chooses Download on an audiobook
  kind: actor
  actor: member
  entities:
  - {entity: audiobook, effect: reads, facts: []}
  contexts:
    iphone:
      place: iphone::household::book
- text: The Product downloads the chapters in the background
  kind: product
  actor: member
  entities:
  - {entity: audiobook, effect: reads, facts: [Chapters, Offline ready]}
  - {entity: downloaded-audiobook, effect: creates, to: Downloading, facts: [Chapters on device, Size]}
  contexts:
    iphone:
      place: iphone::household::book
- text: The Product marks the audiobook downloaded once every chapter is on the phone
  kind: product
  actor: member
  entities:
  - {entity: downloaded-audiobook, effect: changes, from: Downloading, to: Downloaded, facts: [Chapters on device, Size]}
  - {entity: audiobook, effect: reads, facts: []}
  contexts:
    iphone:
      place: iphone::household::book
---

# Download an audiobook

## Trigger

A person will be without a connection.

## Outcome

The whole audiobook plays offline.

## Decision points

### Network

Is the phone allowed to download over cellular?

- Any network → Chapters download on Wi-Fi or cellular
- Wi-Fi only → Chapters wait for Wi-Fi

## Edge cases

- An expired download link is renewed from the server instead of failing the chapter.
- Cancelling a download in progress discards the partial chapters.
