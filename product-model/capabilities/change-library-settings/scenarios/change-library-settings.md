---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator changes the library settings and saves
  kind: actor
  actor: administrator
  entities:
  - {entity: library-settings, effect: reads, facts: []}
  contexts:
    web:
      place: web::administration::library-settings
- text: The Product saves them; they apply to the next grabs and imports
  kind: product
  actor: administrator
  entities:
  - {entity: library-settings, effect: changes, facts: [Post-processing, Movies folder, Shows folder, Downloads folder, File operation, Movie naming, Episode naming, Default movie profile, Default show profile, Active indexer manager, Seed targets, Automatic seeding release, Blocked file types, Minimum free space, Download checks]}
  - {entity: grab, effect: reads, facts: []}
  contexts:
    web:
      place: web::administration::library-settings
---

# Change library settings

## Trigger

The instance is being set up or its storage changed.

## Outcome

New grabs, imports and seeding follow the new settings.

## Edge cases

- Only an indexer manager that is enabled can be made active.
