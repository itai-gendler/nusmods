---
appliesTo:
  - { type: capability, id: import-planner }
  - { type: entity, id: planned-course, effect: removes }
references:
  - { kind: code, role: implementation, target: website/src/reducers/planner.ts }
---

# Importing a planner replaces the whole planner

A planner file takes the place of every planned course and every planner setting; nothing is merged.
