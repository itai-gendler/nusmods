---
domain: timetable
availability:
  - { place: web::public }
references:
  - { kind: code, role: implementation, target: website/src/views/timetable/ModuleTombstone.tsx }
  - { kind: code, role: implementation, target: website/src/reducers/undoHistory.ts#computeUndoStacks }
  - { kind: code, role: implementation, target: website/src/reducers/index.ts }
---

# Undo a timetable change

Bring back the timetable as it was before the latest removal of a course or import of a shared timetable.
