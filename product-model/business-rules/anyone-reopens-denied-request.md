---
appliesTo:
- {type: entity, id: request, effect: changes, to: Pending}
permits:
- {actors: [member, administrator]}
references:
- {kind: code, role: implementation, target: apps/api/src/services/mediaRequests.ts#createRequest}
---

# Any signed-in person reopens a denied request by asking for the title again

Asking again for a denied title puts the same request back in front of the administrators under the new requester.
