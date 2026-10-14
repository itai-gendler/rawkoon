---
entities:
- {entity: movie, shows: [Title]}
- {entity: show, shows: [Title]}
- {entity: request, shows: [Requested]}
references:
- {kind: code, role: implementation, target: apps/ios/Rawkoon/Views/Discover/MediaSearch.swift}
- {kind: code, role: implementation, target: apps/ios/Rawkoon/Views/DiscoverView.swift}
---

# Discover

Search and suggestions, with Request on titles the library lacks.
