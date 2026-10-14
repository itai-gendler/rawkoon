---
entities:
- {entity: movie, shows: [Title, Poster, Added]}
- {entity: show, shows: [Title, Poster, Added]}
- {entity: listening-progress, shows: [Position, Finished]}
- {entity: reading-progress, shows: [Offset, Finished]}
- {entity: attention-alert, shows: [Kind, Detail, Opened]}
- {entity: grab, shows: [Release title, Import error]}
references:
- {kind: code, role: implementation, target: apps/web/src/pages/_component/HomePage.tsx}
- {kind: code, role: implementation, target: apps/web/src/pages/_component/LibraryAttentionPanel.tsx}
---

# Home

The landing page: recently added titles, upcoming releases, what the person is listening to or reading, and for administrators the Library attention panel and download activity.
