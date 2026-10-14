---
appliesTo:
- {type: capability, id: search-now}
- {type: capability, id: search-wanted-titles}
- {type: entity, id: integration-settings, facts: [AI provider]}
references:
- {kind: code, role: implementation, target: apps/api/src/services/aiProvider/client.ts#pickReleaseWithAi}
- {kind: doc, role: intent, target: docs/library/ai-release-picks.md}
---

# The language model only chooses among releases the profile allows

It sees at most the ten best-scored releases with seeders, never download links, and a pick that is not one of them is ignored; when it cannot help, the classic scorer's choice is grabbed.
