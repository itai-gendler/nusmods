---
domain: timetable
availability:
  - { place: web::public }
references:
  - { kind: code, role: implementation, target: website/src/actions/timetables.ts#enableTaModule }
  - { kind: code, role: implementation, target: website/src/views/timetable/TimetableModulesTable.tsx }
---

# Enable TA mode

Mark a course as one the student teaches, so they can choose any number of its lessons of each type, as a teaching assistant takes several tutorials.
