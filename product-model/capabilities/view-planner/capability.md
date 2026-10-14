---
domain: planner
availability:
  - { place: web::public }
references:
  - { kind: code, role: implementation, target: website/src/views/planner/PlannerContainer/PlannerContainer.tsx }
  - { kind: code, role: implementation, target: website/src/views/planner/PlannerYear.tsx }
  - { kind: code, role: implementation, target: website/src/views/planner/PlannerSemester.tsx }
  - { kind: code, role: implementation, target: website/src/views/planner/PlannerModule.tsx }
  - { kind: code, role: implementation, target: website/src/selectors/planner.ts#getAcadYearModules }
  - { kind: code, role: implementation, target: website/src/utils/planner.ts#checkPrerequisite }
---

# View the planner

See the degree plan from matriculation to graduation, year by year and semester by semester, with exemptions, iBLOCs and courses planned to take, the units of each semester and in all, and warnings on courses whose prerequisites are unmet, that are not offered in their semester, whose exams clash, that appear twice in a semester or that NUSMods has no information on.
