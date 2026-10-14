---
actors:
- administrator
- member
access: authenticated
references:
- {kind: code, role: implementation, target: apps/web/src/lib/routing/navigation.ts#navSections}
---

# Household

Everything a signed-in person reaches from the main navigation: Home, Calendar,
Library, Books, Requests, Browse, For You, Watchlist and Collections, their
notifications and their own settings. Administrators manage titles from the
same pages.
