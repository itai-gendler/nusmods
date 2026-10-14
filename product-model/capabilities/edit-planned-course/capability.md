---
domain: planner
availability:
  - { place: web::public }
references:
  - { kind: code, role: implementation, target: website/src/views/planner/CustomModuleForm.tsx }
  - { kind: code, role: implementation, target: website/src/actions/planner.ts#addCustomModule }
---

# Edit a planned course

Give a course code in the plan its own units and title, for courses NUSMods has no or wrong information on.
