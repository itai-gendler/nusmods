---
kind: person
acts: external
relations:
  - { entity: timetable, verb: owns, cardinality: one-to-many }
  - { entity: planner, verb: owns, cardinality: one-to-one }
  - { entity: cpex-submission, verb: owns, cardinality: one-to-one }
references:
  - { kind: code, role: implementation, target: website/src/reducers/settings.ts }
  - { kind: code, role: implementation, target: website/src/reducers/theme.ts }
  - { kind: code, role: implementation, target: website/src/types/reducers.ts }
---

# Student

A person using NUSMods to find courses and plan their semesters. Anyone can use NUSMods without signing in; a student signs in with their NUS account only to take part in the Course Planning Exercise. What they build and choose is kept in their own browser.

## Information kept

- **Color scheme** — Night Mode: light, dark, or following the device; it starts following the device
- **Theme** — the set of colours timetable courses are drawn in; it starts as Eighties
- **Prerequisite tree direction** — whether a course page's prerequisite tree grows to the left or the right
- **CourseReg reminders** — whether reminders of CourseReg rounds show at all; they start on
- **Course type** — Undergraduate or Graduate, choosing which CourseReg schedule applies and which programme-type requisites the planner checks; it starts as Undergraduate
- **Dismissed reminders** — the CourseReg rounds the student dismissed this semester
- **Beta testing** — whether the student tries features still in beta
- **Usage tracking** — whether anonymous usage analytics run in this browser
- **Load reviews manually** — whether course reviews load only when the student asks
- **Contact details** — the name, email and matriculation number the student last gave when reporting a course error, offered again next time
