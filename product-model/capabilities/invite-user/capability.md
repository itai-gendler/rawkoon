---
domain: users
availability:
- {place: 'web::administration'}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/admin/adminUserRoutes.ts}
- {kind: code, role: implementation, target: apps/web/src/pages/settings/_component/users/UserProvisioningSection.tsx}
---

# Invite a user

An administrator generates a single-use invitation link for an email address, choosing its language and whether the account will be an administrator.
