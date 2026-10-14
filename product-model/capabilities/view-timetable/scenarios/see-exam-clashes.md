---
kind: alternative
routes:
  web: Web
steps:
  - text: "The Student opens the Timetable"
    kind: actor
    actor: student
    entities:
      - { entity: timetable, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "Two shown timetable courses outside TA mode have exams on the same day whose times overlap"
    kind: condition
    actor: student
    entities:
      - { entity: timetable-course, effect: reads, facts: [TA mode] }
      - { entity: course, effect: reads, facts: [Exam] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product warns that there are clashes in the exam timetable and lists the clashing courses under each clash date, ahead of the other courses"
    kind: product
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [Code, Title, Exam] }
      - { entity: timetable, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
---

# See exam clashes

## Trigger

Two shown courses in the timetable have exams that overlap on the same day.

## Outcome

The student is warned and sees which courses clash on which date.

## Edge cases

- Hidden courses and courses in TA mode never make a clash.
