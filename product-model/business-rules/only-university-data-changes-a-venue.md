---
appliesTo:
  - { type: entity, id: venue, effect: changes }
permits:
  - { unattended: true }
references:
  - { kind: code, role: implementation, target: scrapers/nus-v2/src/tasks/CollateVenues.ts }
---

# Only the university's data changes a venue's lessons

A venue's lessons and occupancy come only from the lessons in the university's timetable data.
