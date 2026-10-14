---
entities:
- {entity: request, shows: [Kind, Title, Year, Poster, Deny reason, Requested], collects: [Quality profile, Deny reason]}
- {entity: quality-profile, shows: [Name]}
references:
- {kind: code, role: implementation, target: apps/ios/Rawkoon/Views/RequestsView.swift}
---

# Requests

Requests and their status; administrators approve or deny the pending ones.
