---
entities:
- {entity: request, shows: [Kind, Title, Year, Poster, Quality profile, Deny reason, Requested, Decided], collects: [Quality profile, Deny reason]}
- {entity: quality-profile, shows: [Name]}
references:
- {kind: code, role: implementation, target: apps/web/src/pages/requests/_component/RequestsPage.tsx}
---

# Requests

Requests and their status; administrators see everyone's and decide the pending ones.
