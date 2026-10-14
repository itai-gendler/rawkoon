---
domain: requests
availability:
- {place: 'web::household'}
- {place: 'iphone::household'}
references:
- {kind: code, role: implementation, target: apps/api/src/services/mediaRequests.ts#approveRequest}
- {kind: code, role: implementation, target: apps/web/src/pages/requests/_component/RequestsPage.tsx}
- {kind: code, role: implementation, target: apps/ios/Rawkoon/Views/RequestsView.swift}
---

# Approve a request

An administrator approves a pending request with a quality profile; the title is added to the library and the requester is told.
