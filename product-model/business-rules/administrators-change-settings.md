---
appliesTo:
- {type: entity, id: library-settings, effect: changes}
- {type: entity, id: general-settings, effect: changes}
- {type: entity, id: integration-settings, effect: changes}
permits:
- {actors: [administrator]}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/settings/index.ts}
- {kind: code, role: implementation, target: apps/api/src/routes/integrations/index.ts}
---

# Only an administrator changes the instance's settings

Library, general, integration and books settings belong to the administration area.
