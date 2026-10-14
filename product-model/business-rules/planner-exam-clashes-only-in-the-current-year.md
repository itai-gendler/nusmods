---
appliesTo:
  - { type: capability, id: view-planner }
  - { type: entity, id: planned-course, facts: [Warnings] }
references:
  - { kind: code, role: implementation, target: website/src/selectors/planner.ts#getAcadYearModules }
  - { kind: code, role: implementation, target: website/src/utils/planner.ts#getConflictToDisplay }
---

# The planner flags exam clashes only in the current academic year

Exam dates are known only for the current academic year, so only its semesters are checked for exam clashes; every year is checked for courses outside their semesters, duplicates in a semester and codes with no information.
