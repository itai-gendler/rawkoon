---
appliesTo:
- {type: capability, id: invite-user}
- {type: capability, id: regenerate-invitation-link}
- {type: entity, id: invitation}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/admin/adminUserRoutes.ts}
---

# An email has at most one pending invitation, and an invitation link lasts seven days

A second invitation for the same address is refused; regenerating replaces the link and restarts the seven days.
