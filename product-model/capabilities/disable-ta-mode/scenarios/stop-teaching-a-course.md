---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student chooses Disable TA on a timetable course in TA mode"
    kind: actor
    actor: student
    entities:
      - { entity: timetable-course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product takes the timetable course out of TA mode and keeps, for each lesson type, the class closest to the lessons it had"
    kind: product
    actor: student
    entities:
      - { entity: timetable-course, effect: changes, facts: [TA mode, Lessons chosen] }
      - { entity: course, effect: reads, facts: [Lessons] }
    contexts: { web: { place: "web::public::timetable" } }
---

# Stop teaching a course

## Trigger

The student no longer teaches the course.

## Outcome

The course has one class of each lesson type, the closest to the lessons chosen in TA mode.
