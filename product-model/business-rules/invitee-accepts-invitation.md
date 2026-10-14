---
appliesTo:
- {type: entity, id: invitation, effect: changes, to: Accepted}
permits:
- {actors: [visitor]}
references:
- {kind: code, role: implementation, target: apps/api/src/auth.ts}
---

# An invitation is accepted only by the person following its link

The link is the invitee's way in; nobody else accepts it for them.
