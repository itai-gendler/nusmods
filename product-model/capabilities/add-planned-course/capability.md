---
availability:
  - { place: web::public }
references:
  - { kind: code, role: implementation, target: website/src/views/planner/AddModule.tsx }
  - { kind: code, role: implementation, target: website/src/views/planner/PlannerContainer/PlannerContainer.tsx#PlannerContainerComponent }
  - { kind: code, role: implementation, target: website/src/views/components/module-info/SaveModuleButton.tsx }
  - { kind: code, role: implementation, target: website/src/actions/planner.ts#addPlannerModule }
  - { kind: code, role: implementation, target: website/src/utils/placeholders/general.ts }
---

# Add a planned course

Put a course, or a placeholder such as "Any GE module", into a semester of the plan, the exemptions or the courses planned to take, from the Planner or a course page.
