---
appliesTo:
  - { type: entity, id: timetable-course, effect: creates }
references:
  - { kind: code, role: implementation, target: website/src/utils/timetables/index.ts#randomModuleLessonConfig }
  - { kind: code, role: implementation, target: website/src/utils/colors.ts }
---

# A new course starts with one random class of each lesson type

A course added to a timetable gets a class picked at random for each of its lesson types, and a colour no other course in the timetable has while the theme has one free.
