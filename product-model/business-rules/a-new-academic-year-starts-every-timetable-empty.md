---
appliesTo:
  - { type: entity, id: timetable }
references:
  - { kind: code, role: implementation, target: website/src/reducers/timetables.ts }
  - { kind: doc, role: context, target: MAINTENANCE.md, title: Maintenance }
---

# A new academic year starts every timetable empty

When NUSMods moves to a new academic year, a student's saved timetables are archived and every semester starts empty; archived timetables are not shown again.
