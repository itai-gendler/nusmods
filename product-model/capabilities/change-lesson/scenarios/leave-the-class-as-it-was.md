---
kind: alternative
routes:
  web: Web
steps:
  - text: "The Student picks a lesson of a timetable course on the timetable"
    kind: actor
    actor: student
    entities:
      - { entity: timetable-course, effect: reads, facts: [Lessons chosen] }
      - { entity: timetable, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product shows every class of that lesson type"
    kind: product
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [Lessons] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Student picks the chosen class again, clicks elsewhere or presses Escape"
    kind: actor
    actor: student
    entities: []
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product stops showing the other classes and keeps the chosen one"
    kind: product
    actor: student
    entities: []
    contexts: { web: { place: "web::public::timetable" } }
---

# Leave the class as it was

## Trigger

The student looks at the other classes but keeps the one they have.

## Outcome

Nothing changes.
