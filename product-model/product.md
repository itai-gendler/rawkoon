---
id: rawkoon
summary: A self-hosted movie, TV, ebook and audiobook library that finds releases through an indexer, hands them to a download client and tracks each title through to the library.
category: media-library
tags:
- self-hosted
- media-library
- download-manager
- audiobooks
authors:
- {name: Samuel Loranger, url: 'https://github.com/samuelloranger'}
license: GPL-3.0-or-later
languages:
- en
- fr
limitations:
- 'There is no open registration: the first account on a new instance becomes its administrator, and every later account is invited or created by an administrator.'
- Rawkoon does not play video; movies and shows are watched in the household's own media player.
- 'Rawkoon does not transfer files itself: releases come from Prowlarr or Jackett and are downloaded by qBittorrent, Transmission or Deluge.'
- The book library stays off until an administrator turns it on, and turning it on needs a stored Google Books key.
- The web app plays audiobooks and reads ebooks only while its tab is open in the foreground; listening offline is the iPhone app's.
references:
- {kind: doc, role: intent, target: README.md, title: README}
- {kind: doc, role: intent, target: PRODUCT.md, title: Product brief}
- {kind: doc, role: intent, target: CONTEXT.md, title: Domain language}
- {kind: doc, role: intent, target: docs/getting-started.md, title: Getting started}
---

# Rawkoon

Rawkoon is a self-hosted library for movies, TV shows, ebooks and audiobooks
with a built-in download manager. An administrator adds titles found through
TMDB and the book providers, Rawkoon searches releases through the household's
indexer manager, hands the chosen release to the download client, and follows
the download until the file is placed in the library. Household members request
titles, browse the library and listen to audiobooks or read ebooks, in the
browser or in the iPhone app.

## Intent

One instance replaces a stack of separate tools: it discovers titles, searches
releases, hands downloads to a client and imports the files, with books in the
same place as movies and shows. Success is a household that can find, request
and receive media from one instance, and listen to audiobooks on an iPhone
without a browser. The administrator's job comes first; household members
request and listen, they do not configure the instance.
