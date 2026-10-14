---
appliesTo:
  - { type: capability, id: edit-planned-course }
  - { type: entity, id: planner, facts: [Custom course details] }
references:
  - { kind: code, role: implementation, target: website/src/selectors/planner.ts }
  - { kind: code, role: implementation, target: website/src/utils/planner.ts#getModuleCredit }
---

# Custom units and title apply wherever the course code is planned

Units and a title entered for a planned course belong to its course code and replace NUSMods' information for every place that code appears in the plan.
