---
appliesTo:
- {type: entity, id: movie, effect: creates}
- {type: entity, id: show, effect: creates}
permits:
- {actors: [administrator]}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/library/libraryListRoutes.ts}
- {kind: doc, role: intent, target: PRODUCT.md, title: Product Principles}
---

# Only an administrator adds a movie or show to the library

Household members ask for titles through requests; an administrator adds them, directly or by approving a request.
