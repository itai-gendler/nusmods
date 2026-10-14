---
appliesTo:
  - { type: capability, id: add-course-to-timetable }
  - { type: entity, id: timetable-course, effect: creates }
references:
  - { kind: code, role: implementation, target: website/src/views/timetable/ModulesSelectContainer.tsx }
---

# A course is added to a timetable only while online

Adding a course needs its lessons, which come from NUSMods online, so the course search is disabled offline.
