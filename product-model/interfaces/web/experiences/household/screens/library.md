---
entities:
- {entity: movie, shows: [Title, Year, Poster, Added]}
- {entity: show, shows: [Title, Year, Poster, Episodes, Downloaded episodes, Added]}
references:
- {kind: code, role: implementation, target: apps/web/src/pages/medias/_component/LibraryPage.tsx}
---

# Library

The movies and shows in the library, with filters, search and sorting.
