---
appliesTo:
  - { type: entity, id: course, effect: changes }
permits:
  - { unattended: true }
references:
  - { kind: code, role: implementation, target: scrapers/nus-v2/src/tasks/DataPipeline.ts }
  - { kind: code, role: implementation, target: website/src/views/modules/ReportError.tsx }
---

# Only the university's data changes a course

A course's information changes only through the refresh; a student who finds an error reports it to the faculty, which corrects it at the source.
