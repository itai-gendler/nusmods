---
domain: planner
availability:
  - { place: web::public }
references:
  - { kind: code, role: implementation, target: website/src/views/planner/PlannerImportButton.tsx }
  - { kind: code, role: implementation, target: website/src/types/schemas/planner.ts }
  - { kind: code, role: implementation, target: website/src/actions/planner.ts#importPlanner }
---

# Import a planner

Replace the plan with one from a planner file.
