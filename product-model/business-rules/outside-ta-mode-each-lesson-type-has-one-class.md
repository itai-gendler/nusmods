---
appliesTo:
  - { type: entity, id: timetable-course, facts: [Lessons chosen] }
references:
  - { kind: code, role: implementation, target: website/src/actions/timetables.ts#validateTimetable }
  - { kind: code, role: implementation, target: website/src/utils/timetables/index.ts }
---

# Outside TA mode a course has exactly one class of each lesson type

A course not in TA mode always has one class of each lesson type the course has that semester; when course data changes so that a chosen class or lesson type no longer exists, NUSMods puts a valid class in its place when the timetable opens.
