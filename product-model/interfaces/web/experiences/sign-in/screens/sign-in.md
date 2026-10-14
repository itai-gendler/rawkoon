---
entities:
- {entity: account, collects: [Email, Password]}
references:
- {kind: code, role: implementation, target: apps/web/src/pages/login/_component/LoginForm.tsx}
---

# Sign in

Where a person signs in with email and password, a passkey or a single sign-on provider.
