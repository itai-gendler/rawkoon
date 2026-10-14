---
appliesTo:
- {type: capability, id: create-administrator-account}
- {type: capability, id: sign-in}
- {type: capability, id: accept-invitation}
references:
- {kind: code, role: implementation, target: apps/api/src/lib/auth.ts}
- {kind: doc, role: intent, target: docs/getting-started.md, title: Sign in}
---

# Accounts are created only by the first setup, an invitation or an administrator

After the first account exists, sign-ups and single sign-on never create accounts.
