---
entities:
- {entity: account, shows: [Email, First name, Last name, Administrator access, Created, Last sign-in], collects: [Email, First name, Last name, Password, Language, Administrator access]}
- {entity: invitation, shows: [Email, Expires, Created, Link], collects: [Email, Language, Administrator]}
references:
- {kind: code, role: implementation, target: apps/web/src/pages/settings/_component/UsersTab.tsx}
---

# Users

The instance's accounts and invitations.
