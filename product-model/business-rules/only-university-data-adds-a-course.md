---
appliesTo:
  - { type: entity, id: course, effect: creates }
permits:
  - { unattended: true }
references:
  - { kind: code, role: implementation, target: scrapers/nus-v2/src/tasks/DataPipeline.ts }
---

# Only the university's data adds a course

Courses enter the catalogue only through the refresh from the university's systems; nobody adds one in NUSMods.
