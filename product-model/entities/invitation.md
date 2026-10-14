---
domain: users
references:
- {kind: code, role: implementation, target: apps/api/src/routes/admin/adminUserRoutes.ts}
---

# Invitation

A single-use link an administrator generates so a person can create their own account.

## Information kept

- **Email** — the address the account will have
- **Language** — the language the new account starts with
- **Administrator** — whether the new account is an administrator
- **Link** — the single-use link to share; shown once when generated
- **Expires** — seven days after the link was generated; past it the list shows the invitation as expired and the link no longer works
- **Created** — when the invitation was made
- **Accepted** — when the account was created from it

## States

### Pending

The link can be followed until it expires.

### Accepted

An account was created from it.

### Revoked

An administrator withdrew it; the link no longer works.
