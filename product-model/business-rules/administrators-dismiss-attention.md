---
appliesTo:
- {type: entity, id: attention-alert, effect: changes}
permits:
- {actors: [administrator]}
- {unattended: true}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/library/libraryAttentionRoutes.ts}
---

# Only an administrator dismisses an attention alert

Rawkoon closes alerts itself when their condition clears.
