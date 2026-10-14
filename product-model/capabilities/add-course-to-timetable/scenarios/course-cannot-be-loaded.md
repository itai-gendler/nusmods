---
kind: edge
routes:
  web: Web
steps:
  - text: "The Student picks a course to add"
    kind: actor
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The course details cannot be loaded"
    kind: condition
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product says it cannot load the course and offers Retry"
    kind: product
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [Code] }
    contexts: { web: { place: "web::public::timetable" } }
---

# Course cannot be loaded

## Trigger

The course details cannot be fetched.

## Outcome

Nothing is added; the student can retry.
