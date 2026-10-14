---
entities:
- {entity: movie, shows: [Title, Sort title, Year, Overview, Poster, Backdrop, Monitored, Quality profile, Search title, Digital release date, Size on disk], collects: [Quality profile, Title, Sort title, Year, Overview, Poster]}
- {entity: show, shows: [Title, Year, Overview, Poster, Backdrop, Monitored, Quality profile, Series status, Seasons, Episodes, Downloaded episodes, Size on disk], collects: [Quality profile, Poster, Backdrop]}
- {entity: episode, shows: [Season, Number, Title, Air date, Monitored]}
- {entity: video-file, shows: [Path, File name, Size, Duration, Resolution, Source, Video codec, HDR, Audio tracks, Subtitle tracks, Languages, Release group, Scanned]}
- {entity: grab, shows: [Release title, Indexer, Grabbed, Completed, AI pick, Failure reason, Import error, Library path, Released from client]}
- {entity: quality-profile, shows: [Name]}
references:
- {kind: code, role: implementation, target: apps/web/src/pages/medias/_component/LibraryItemPage.tsx}
- {kind: code, role: implementation, target: apps/web/src/pages/medias/_component/LibraryManagementPanel.tsx}
- {kind: code, role: implementation, target: apps/web/src/pages/medias/_component/InteractiveSearchPanel.tsx}
---

# Title

One movie or show in the library: its details, seasons and episodes, files and Download history, and for administrators its release search and management.
