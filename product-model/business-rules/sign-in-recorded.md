---
appliesTo:
- {type: entity, id: account, effect: changes, facts: [Last sign-in]}
permits:
- {actors: [visitor]}
references:
- {kind: code, role: implementation, target: apps/api/src/lib/auth.ts}
---

# Signing in records the account's last sign-in

Every sign-in, by password, passkey or provider, stamps the account.
