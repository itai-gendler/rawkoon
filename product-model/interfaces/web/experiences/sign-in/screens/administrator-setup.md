---
entities:
- {entity: account, collects: [First name, Last name, Email, Password]}
references:
- {kind: code, role: implementation, target: apps/web/src/pages/login/_component/SetupForm.tsx}
---

# Administrator setup

Where the first person on a new instance creates the administrator account.
