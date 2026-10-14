---
appliesTo:
  - { type: entity, id: planner, facts: [Matriculation year, Graduation year] }
references:
  - { kind: code, role: implementation, target: website/src/reducers/planner.ts }
---

# Graduation is never before matriculation

Choosing a matriculation year after the graduation year moves the graduation year to it, and the other way round.
