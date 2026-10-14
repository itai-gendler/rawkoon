---
entities:
- {entity: movie, shows: [Title]}
- {entity: show, shows: [Title]}
- {entity: request, shows: [Requested]}
references:
- {kind: code, role: implementation, target: apps/web/src/pages/medias/_component/ExplorePage.tsx}
- {kind: code, role: implementation, target: apps/web/src/pages/medias/_component/ExploreCardActions.tsx}
---

# Browse

TMDB search and Discover lists, with a title's details, Add to Library for administrators and Request for household members.
