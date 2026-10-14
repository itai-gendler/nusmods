---
kind: alternative
routes:
  web: Web
steps:
  - text: "The Student ticks No Exam Clash for a semester, or No Exam"
    kind: actor
    actor: student
    entities: []
    contexts: { web: { place: "web::public::course-finder" } }
  - text: "The Product leaves out courses with an exam at the same date and time as a course in that semester's timetable, or every course with an exam"
    kind: product
    actor: student
    entities:
      - { entity: timetable-course, effect: reads, facts: [Course] }
      - { entity: course, effect: reads, facts: [Exam] }
      - { entity: timetable, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::course-finder" } }
---

# Filter out exam clashes

## Trigger

The student wants courses whose exams fit their timetable.

## Outcome

Only courses with no exam at the same time as one in the student's timetable for that semester are listed.

## Edge cases

- No Exam Clash is offered only for semesters whose timetable has courses with exams.
