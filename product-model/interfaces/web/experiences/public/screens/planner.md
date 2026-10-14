---
entities:
  - { entity: planner, shows: [Matriculation year, Graduation year, iBLOCs, Ignore prerequisite checking, Custom course details], collects: [Matriculation year, Graduation year, iBLOCs, Ignore prerequisite checking, Custom course details] }
  - { entity: planned-course, shows: [Course, Placeholder, Year, Semester, Position, Warnings] }
  - { entity: course, shows: [Code, Title, Units, Exam] }
  - { entity: timetable, shows: [Semester] }
  - { entity: timetable-course, shows: [Course] }
entryPoints:
  - web: /planner
references:
  - { kind: code, role: implementation, target: website/src/views/planner/PlannerContainer/PlannerContainer.tsx }
---

# Course Planner

The student's degree plan, year by year and semester by semester, with exemptions, courses they plan to take, and its settings.
