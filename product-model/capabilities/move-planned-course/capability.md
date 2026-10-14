---
domain: planner
availability:
  - { place: web::public }
references:
  - { kind: code, role: implementation, target: website/src/views/planner/PlannerContainer/PlannerContainer.tsx#PlannerContainerComponent }
  - { kind: code, role: implementation, target: website/src/reducers/planner.ts }
  - { kind: code, role: implementation, target: website/src/actions/planner.ts#movePlannerModule }
---

# Move a planned course

Drag a planned course to another place in its semester, to another semester or year, or between the plan and the exemptions or Plan to Take.
