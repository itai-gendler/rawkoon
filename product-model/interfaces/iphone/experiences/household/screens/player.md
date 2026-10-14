---
entities:
- {entity: audiobook, shows: [Chapters, Duration]}
- {entity: listening-progress, shows: [Position]}
- {entity: downloaded-audiobook, shows: [Chapters on device]}
references:
- {kind: code, role: implementation, target: apps/ios/Rawkoon/Views/PlayerView.swift}
---

# Now Playing

The audiobook player, with chapters and lock-screen controls.
