---
domain: users
availability:
- {place: 'web::administration'}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/admin/adminUserRoutes.ts}
---

# Regenerate an invitation link

An administrator replaces a pending invitation's link with a new one, valid for another seven days.
