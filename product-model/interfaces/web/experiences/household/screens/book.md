---
entities:
- {entity: book, shows: [Title, Subtitle, Authors, Overview, Cover, Language, Published, Series, Narrators, Genres, Publisher, Page count, Rating, ISBN, Metadata sources], collects: [Title, Subtitle, Series, Narrators, Genres, Publisher, Page count, Published, Language, Overview, Cover, ISBN]}
- {entity: ebook, shows: [Monitored, Quality profile, Size on disk], collects: [Quality profile]}
- {entity: audiobook, shows: [Monitored, Quality profile, Narrators, Duration, Size on disk], collects: [Quality profile]}
- {entity: book-file, shows: [File name, Size, Format, Retail, Audio bitrate]}
- {entity: read-badge, shows: [Read on]}
- {entity: book-quality-profile, shows: [Name, Kind]}
- {entity: grab, shows: [Release title, Grabbed]}
references:
- {kind: code, role: implementation, target: apps/web/src/pages/books/_component/BookDetailPage.tsx}
- {kind: code, role: implementation, target: apps/web/src/pages/books/_component/EditionPanel.tsx}
---

# Book

One book: its details, its editions with their files and state, Listen and Read, and for administrators release search and management.
