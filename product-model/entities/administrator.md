---
kind: person
acts: external
relations:
- {entity: account, verb: has, cardinality: one-to-one}
references:
- {kind: code, role: implementation, target: apps/api/src/middleware/hono/auth.ts#requireAdmin}
- {kind: doc, role: intent, target: PRODUCT.md, title: Users}
---

# Administrator

A person who administers the instance: adds and removes titles, chooses releases, decides requests, manages accounts and changes the settings. The first account on a new instance is an administrator.
