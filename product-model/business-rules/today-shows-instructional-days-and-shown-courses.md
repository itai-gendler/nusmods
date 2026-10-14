---
appliesTo:
  - { type: capability, id: view-today }
  - { type: entity, id: timetable-course, facts: [Lessons chosen] }
references:
  - { kind: code, role: implementation, target: website/src/views/today/TodayContainer/TodayContainer.tsx }
  - { kind: code, role: implementation, target: website/src/utils/timetables/index.ts#isLessonAvailable }
---

# Today shows lessons only on teaching days and of shown courses

Today lists a lesson only on a day in an instructional week that is not a public holiday, only in the weeks the lesson runs, and never for a hidden course. Times are Singapore time wherever the student is.
