---
kind: alternative
routes:
  web: Web
steps:
  - text: "The Student opens a course page"
    kind: actor
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::course-page" } }
  - text: "A course in the student's timetable for that semester has its exam at the same date and time"
    kind: condition
    actor: student
    entities:
      - { entity: timetable-course, effect: reads, facts: [Course] }
      - { entity: course, effect: reads, facts: [Exam] }
      - { entity: timetable, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::course-page" } }
  - text: "The Product warns under that semester's exam that those courses have exams at the same time"
    kind: product
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [Code] }
    contexts: { web: { place: "web::public::course-page" } }
---

# See an exam clash warning

## Trigger

The course's exam is at the same time as one in the student's timetable.

## Outcome

The student is warned which of their courses have exams at the same time.
