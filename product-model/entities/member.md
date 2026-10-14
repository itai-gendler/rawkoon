---
kind: person
acts: external
relations:
- {entity: account, verb: has, cardinality: one-to-one}
- {entity: request, verb: requests, cardinality: one-to-many}
references:
- {kind: code, role: implementation, target: apps/api/src/middleware/hono/auth.ts#requireUser}
- {kind: doc, role: intent, target: PRODUCT.md, title: Users}
---

# Member

A household member: browses the library, requests titles, keeps a watchlist, and listens to audiobooks or reads ebooks. Members do not administer the instance.
