---
appliesTo:
  - { type: capability, id: optimise-timetable }
  - { type: journey, id: adopt-an-optimised-timetable }
references:
  - { kind: code, role: implementation, target: website/api/optimiser/_modules/modules.go }
  - { kind: code, role: implementation, target: website/api/optimiser/_solver/solver.go }
  - { kind: doc, role: intent, target: website/api/optimiser/README.md, title: Optimiser README }
---

# Optimised timetables never break free days or the chosen hours

The optimiser never puts a physical lesson on a chosen free day or outside the earliest and latest times; lunch breaks, consecutive hours, gaps and walking distance are preferences it weighs. Lessons attended by recording are exempt from free days and hours.
