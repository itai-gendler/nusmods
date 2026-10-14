---
appliesTo:
  - { type: capability, id: view-timetable }
  - { type: entity, id: course, facts: [Units] }
references:
  - { kind: code, role: implementation, target: website/src/views/timetable/ModulesTableFooter.tsx#countShownMCs }
---

# Active units leave out hidden and TA mode courses

Total units count every course in the timetable; active units, shown when they differ, count only shown courses outside TA mode.
