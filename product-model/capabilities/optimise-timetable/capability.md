---
availability:
  - { place: web::public }
references:
  - { kind: code, role: implementation, target: website/src/views/optimiser/OptimiserContainer/OptimiserContent.tsx }
  - { kind: code, role: implementation, target: website/src/views/optimiser/OptimiserForm/OptimiserForm.tsx }
  - { kind: code, role: implementation, target: website/src/views/optimiser/OptimiserButton.tsx }
  - { kind: code, role: implementation, target: website/src/views/optimiser/OptimiserResults.tsx }
  - { kind: code, role: implementation, target: website/src/utils/optimiser.ts }
  - { kind: code, role: implementation, target: website/api/optimiser/optimise.go }
  - { kind: code, role: implementation, target: website/api/optimiser/_solver/solver.go }
  - { kind: doc, role: intent, target: website/api/optimiser/README.md, title: Optimiser README }
---

# Optimise a timetable

Have NUSMods propose classes for the courses in the current semester's timetable that keep chosen days free of physical lessons, keep lessons within chosen hours, leave room for lunch, limit consecutive hours and shorten walks between venues, with chosen classes pinned and chosen lessons attended by recording. Still in beta.
