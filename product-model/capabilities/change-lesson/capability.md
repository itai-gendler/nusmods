---
domain: timetable
availability:
  - { place: web::public }
references:
  - { kind: code, role: implementation, target: website/src/views/timetable/TimetableContent.tsx#TimetableContent }
  - { kind: code, role: implementation, target: website/src/actions/timetables.ts#changeLesson }
  - { kind: code, role: implementation, target: website/src/utils/timetables/index.ts }
---

# Change a lesson

Move a course to another class of one lesson type: picking a lesson on the timetable shows every class of that type, and picking one of them makes it the chosen class.
