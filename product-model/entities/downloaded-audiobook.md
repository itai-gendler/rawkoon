---
domain: books
references:
- {kind: code, role: implementation, target: apps/ios/Rawkoon/AppModel+Downloads.swift}
- {kind: code, role: implementation, target: apps/ios/Rawkoon/ChapterDownloader.swift}
---

# Downloaded audiobook

An audiobook's chapters kept on an iPhone for listening offline.

## Information kept

- **Chapters on device** — which chapters are on the phone
- **Size** — the space the chapters take on the phone

## States

### Downloading

Chapters are downloading in the background.

### Downloaded

Every chapter is on the phone.
