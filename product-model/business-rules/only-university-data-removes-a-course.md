---
appliesTo:
  - { type: entity, id: course, effect: removes }
permits:
  - { unattended: true }
references:
  - { kind: code, role: implementation, target: scrapers/nus-v2/src/tasks/DataPipeline.ts }
---

# Only the university's data removes a course

A course leaves the year's catalogue only when the university no longer lists it as active.
