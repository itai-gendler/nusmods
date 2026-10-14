---
domain: timetable
availability:
  - { place: web::public }
references:
  - { kind: code, role: implementation, target: website/src/views/timetable/TimetableContainer.tsx }
  - { kind: code, role: implementation, target: website/src/views/timetable/TimetableContent.tsx }
  - { kind: code, role: implementation, target: website/src/views/timetable/TimetableModulesTable.tsx }
  - { kind: code, role: implementation, target: website/src/views/timetable/ModulesTableFooter.tsx }
  - { kind: code, role: implementation, target: website/src/views/components/semester-switcher/SemesterSwitcher.tsx }
  - { kind: code, role: implementation, target: website/src/utils/timetables/exams.ts }
---

# View a semester timetable

Open the timetable of one semester: its shown courses' lessons on the week grid, and beside it every course in it with its exam date and duration, its units, the total units and, where hidden or taught courses leave some out, the active units. Exam clashes are listed first. The student moves between semesters with the semester switcher.
