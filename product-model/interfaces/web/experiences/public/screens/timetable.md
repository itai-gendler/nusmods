---
entities:
  - { entity: timetable, shows: [Semester] }
  - { entity: timetable-course, shows: [Course, Lessons chosen, Color, TA mode] }
  - { entity: course, shows: [Code, Title, Units, Exam, Lessons] }
entryPoints:
  - web: /timetable/sem-1
references:
  - { kind: code, role: implementation, target: website/src/views/timetable/TimetableContainer.tsx }
  - { kind: code, role: implementation, target: website/src/views/timetable/TimetableContent.tsx }
---

# Timetable

One semester's timetable: its lessons on the week grid or its exams on a calendar, the list of its courses with exam dates and units, and the timetable shared through a link before it is imported.
