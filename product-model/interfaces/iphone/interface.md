---
type: mobile-app
actors:
- visitor
- administrator
- member
references:
- {kind: code, role: implementation, target: apps/ios/Rawkoon/RawkoonApp.swift}
- {kind: code, role: implementation, target: apps/ios/Rawkoon/RootTabsView.swift}
- {kind: doc, role: intent, target: docs/getting-started.md, title: Use the iPhone app}
---

# iPhone app

The native iPhone app. A person points it at their instance and signs in with
their Rawkoon account; it manages requests, plays audiobooks with chapters
downloaded to the phone, and reads ebooks.
