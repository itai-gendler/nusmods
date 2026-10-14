---
domain: timetable
availability:
  - { place: web::public }
references:
  - { kind: code, role: implementation, target: website/src/actions/timetables.ts#disableTaModule }
  - { kind: code, role: implementation, target: website/src/utils/timetables/index.ts }
---

# Disable TA mode

Take a course out of TA mode, back to one class of each lesson type.
