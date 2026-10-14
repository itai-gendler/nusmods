---
relations:
  - { entity: timetable-course, verb: holds, cardinality: one-to-many }
references:
  - { kind: code, role: implementation, target: website/src/reducers/timetables.ts }
  - { kind: code, role: implementation, target: website/src/types/timetables.ts }
---

# Timetable

A student's timetable for one semester of the academic year.

## Information kept

- **Semester** — Semester 1, Semester 2, Special Term I or Special Term II
- **Academic year** — the academic year it was built for

## States

### Current

Built for the academic year NUSMods is showing.

### Archived

Set aside when a new academic year began; no longer shown.
