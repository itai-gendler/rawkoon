---
appliesTo:
- {type: entity, id: attention-alert, effect: reads}
permits:
- {actors: [administrator]}
- {unattended: true}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/library/libraryAttentionRoutes.ts}
---

# Only an administrator sees the Library attention panel

Attention alerts are about the download pipeline, which members do not run.
