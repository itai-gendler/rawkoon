---
appliesTo:
- {type: capability, id: change-user-role}
- {type: capability, id: delete-user}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/admin/adminUserRoutes.ts}
---

# The instance always keeps an administrator

The last administrator cannot be made a regular user, and no administrator can delete their own account.
