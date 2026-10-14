---
domain: planner
relations:
  - { entity: planned-course, verb: holds, cardinality: one-to-many }
references:
  - { kind: code, role: implementation, target: website/src/reducers/planner.ts }
  - { kind: code, role: implementation, target: website/src/types/reducers.ts }
---

# Planner

A student's plan of courses across the years of their degree.

## Information kept

- **Matriculation year** — the academic year the student matriculated in; the plan starts there
- **Graduation year** — the academic year the student expects to graduate in; the plan ends there
- **iBLOCs** — whether the student took courses through iBLOCs before matriculating
- **Ignore prerequisite checking** — whether prerequisite warnings are turned off
- **Custom course details** — the units and title the student entered for a course code, used wherever that code appears in the plan
