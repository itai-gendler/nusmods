---
availability:
  - { place: web::public }
references:
  - { kind: code, role: implementation, target: website/src/actions/timetables.ts#addModule }
  - { kind: code, role: implementation, target: website/src/views/timetable/ModulesSelectContainer.tsx }
  - { kind: code, role: implementation, target: website/src/views/components/module-info/AddModuleDropdown.tsx }
  - { kind: code, role: implementation, target: website/src/views/planner/ModuleMenu.tsx }
  - { kind: code, role: implementation, target: website/src/utils/timetables/index.ts#randomModuleLessonConfig }
---

# Add a course to a timetable

Put a course into a semester's timetable, from the Timetable's course search, a course page or the planner. NUSMods gives it one class of each lesson type to start, which the student then changes.
