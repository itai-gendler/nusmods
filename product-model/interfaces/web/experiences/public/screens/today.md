---
entities:
  - { entity: timetable-course, shows: [Course, Lessons chosen, Color] }
  - { entity: venue, shows: [Name, Location] }
entryPoints:
  - web: /today
references:
  - { kind: code, role: implementation, target: website/src/views/today/TodayContainer/TodayContainer.tsx }
---

# Today

The student's lessons for today and the next six days, with where each one is.
