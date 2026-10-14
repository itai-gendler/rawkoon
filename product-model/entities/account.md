---
domain: users
relations:
- {entity: notification, verb: receives, cardinality: one-to-many}
- {entity: watchlist-item, verb: keeps, cardinality: one-to-many}
- {entity: dismissed-title, verb: dismissed, cardinality: one-to-many}
- {entity: listening-progress, verb: keeps, cardinality: one-to-many}
- {entity: reading-progress, verb: keeps, cardinality: one-to-many}
- {entity: read-badge, verb: keeps, cardinality: one-to-many}
references:
- {kind: code, role: implementation, target: apps/api/prisma/schema.prisma}
- {kind: code, role: implementation, target: apps/api/src/lib/auth.ts}
---

# Account

A person's account on the instance, whatever their role.

## Information kept

- **Email** — the address the person signs in with; one account per address
- **First name** — the person's first name
- **Last name** — the person's last name
- **Avatar** — the person's profile picture
- **Language** — English or French; the language of the notifications the person receives
- **Password** — the password for signing in with email; at least eight characters
- **Passkeys** — the passkeys the person registered for signing in without a password
- **Administrator access** — whether the person holds the administrator role
- **Last sign-in** — when the person last signed in
- **Notification preferences** — the kinds of notification the person turned off; every kind is on until turned off
- **Created** — when the account was created
