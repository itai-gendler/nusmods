---
domain: timetable
availability:
  - { place: web::public }
references:
  - { kind: code, role: implementation, target: website/src/views/timetable/TimetableModulesTable.tsx }
  - { kind: code, role: implementation, target: website/src/actions/timetables.ts#hideLessonInTimetable }
---

# Hide a course

Keep a course in the timetable without drawing its lessons, such as one the student is still deciding on.
