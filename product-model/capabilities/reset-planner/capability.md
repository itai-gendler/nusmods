---
domain: planner
availability:
  - { place: web::public }
references:
  - { kind: code, role: implementation, target: website/src/views/planner/PlannerClearButton.tsx }
  - { kind: code, role: implementation, target: website/src/actions/planner.ts#clearPlanner }
---

# Reset the planner

Empty the plan and put its settings back to their defaults, after confirming.
