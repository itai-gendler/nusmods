---
appliesTo:
  - { type: capability, id: view-planner }
  - { type: entity, id: planned-course, facts: [Warnings] }
references:
  - { kind: code, role: implementation, target: website/src/selectors/planner.ts#getAcadYearModules }
  - { kind: code, role: implementation, target: website/src/selectors/planner.ts#getPrereqModuleCode }
  - { kind: code, role: implementation, target: website/src/utils/planner.ts#checkPrerequisite }
---

# Planner prerequisites are checked against earlier semesters and exemptions

A planned course's prerequisites are met only by courses planned in earlier semesters, exemptions and iBLOCs; a variant code such as CS1010S also meets a requirement for its base code CS1010. Cohort and programme-type conditions read the matriculation year and the student's course type. Turning on Ignore prerequisite checking removes these warnings.
