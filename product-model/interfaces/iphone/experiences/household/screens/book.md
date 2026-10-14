---
entities:
- {entity: audiobook, shows: [Narrators, Duration, Offline ready]}
- {entity: ebook, shows: [Size on disk]}
- {entity: downloaded-audiobook, shows: [Chapters on device, Size]}
references:
- {kind: code, role: implementation, target: apps/ios/Rawkoon/Views/BookView.swift}
---

# Book

One book in the app: its audiobook and ebook, Listen, Read, and the audiobook's download to the phone.
