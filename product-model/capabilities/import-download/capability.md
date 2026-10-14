---
availability:
- {place: 'web::household'}
references:
- {kind: code, role: implementation, target: apps/api/src/services/downloadOutcome.ts#finishPostProcess}
- {kind: code, role: implementation, target: apps/api/src/services/postProcessorSingle.ts}
- {kind: code, role: implementation, target: apps/api/src/services/postProcessorSeasonPack.ts}
- {kind: code, role: implementation, target: apps/api/src/services/postProcessorBook.ts}
- {kind: doc, role: intent, target: docs/library/downloads-and-files.md, title: What happens at completion}
- {kind: doc, role: intent, target: CONTEXT.md, title: Post-process}
---

# Import a download

When post-processing is on, Rawkoon places each finished download into the library: it finds the file, names it by the template, hardlinks or moves it into the library folder, scans it and records it.
