---
appliesTo:
  - { type: capability, id: view-timetable }
  - { type: entity, id: timetable-course, facts: [TA mode] }
references:
  - { kind: code, role: implementation, target: website/src/utils/timetables/exams.ts#findExamClashes }
  - { kind: code, role: implementation, target: website/src/views/timetable/TimetableContent.tsx#TimetableContent }
  - { kind: code, role: implementation, target: website/src/views/components/module-info/ModuleExamClash.tsx }
  - { kind: code, role: implementation, target: website/src/views/modules/ModuleFinderSidebar.tsx }
---

# Exam clashes count only shown courses outside TA mode

On the Timetable, two exams clash when they fall on the same day and their times overlap; hidden courses and courses in TA mode never clash. The course page and the course finder's No Exam Clash filter compare exams at the same date and time.
