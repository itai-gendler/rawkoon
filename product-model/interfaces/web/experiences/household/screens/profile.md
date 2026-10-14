---
entities:
- {entity: account, shows: [Email, First name, Last name, Avatar], collects: [First name, Last name, Avatar, Password]}
references:
- {kind: code, role: implementation, target: apps/web/src/pages/settings/_component/ProfileForm.tsx}
---

# Profile

The person's own profile and password.
