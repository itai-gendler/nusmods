---
appliesTo:
  - { type: capability, id: import-shared-timetable }
  - { type: entity, id: timetable-course, effect: removes }
references:
  - { kind: code, role: implementation, target: website/src/views/timetable/TimetableContainer.tsx#TimetableContainerComponent }
---

# Importing a shared timetable replaces the saved one

An imported timetable takes the place of every course in the student's saved timetable for that semester, rather than adding to it; until the student imports, a shared timetable is shown read-only and changes nothing.
