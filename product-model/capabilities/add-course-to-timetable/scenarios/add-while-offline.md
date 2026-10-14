---
kind: edge
routes:
  web: Web
steps:
  - text: "The Student opens the Timetable while offline"
    kind: actor
    actor: student
    entities:
      - { entity: timetable, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The student is offline"
    kind: condition
    actor: student
    entities: []
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product disables the course search and says the student needs to be online to add courses"
    kind: product
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
---

# Add while offline

## Trigger

The student tries to add a course without a connection.

## Outcome

Nothing is added; the student is told to go online.
