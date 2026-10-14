---
entities:
- {entity: invitation, shows: [Email]}
- {entity: account, collects: [First name, Last name, Password]}
references:
- {kind: code, role: implementation, target: apps/web/src/pages/accept-invitation.tsx}
---

# Accept invitation

Where an invitee creates their account from an invitation link.
