---
type: web
actors:
- visitor
- administrator
- member
entryPoints:
- {web: /}
- {web: /login}
references:
- {kind: code, role: implementation, target: apps/web/src/router.tsx}
- {kind: code, role: implementation, target: apps/web/src/lib/routing/navigation.ts#navSections}
- {kind: code, role: implementation, target: apps/web/src/pages/__root.tsx}
---

# Web app

The browser app each instance serves. People sign in there; household members
browse the library, request titles and listen or read; administrators also run
the library, the downloads and the instance's settings.
