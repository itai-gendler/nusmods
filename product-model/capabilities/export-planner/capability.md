---
domain: planner
availability:
  - { place: web::public }
references:
  - { kind: code, role: implementation, target: website/src/views/planner/PlannerExportButton.tsx }
  - { kind: code, role: implementation, target: website/src/actions/export.ts#downloadPlanner }
---

# Export the planner

Download the whole plan, with its settings and custom course details, as a file.
