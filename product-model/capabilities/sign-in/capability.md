---
availability:
- {place: 'web::sign-in'}
- {place: 'iphone::sign-in'}
references:
- {kind: code, role: implementation, target: apps/api/src/lib/auth.ts}
- {kind: code, role: implementation, target: apps/web/src/pages/login/_component/LoginForm.tsx}
- {kind: code, role: implementation, target: apps/ios/Rawkoon/AppModel+Auth.swift}
---

# Sign in

A person signs in with their email and password, a passkey, or a configured single sign-on provider. In the iPhone app they first give their instance's address.
