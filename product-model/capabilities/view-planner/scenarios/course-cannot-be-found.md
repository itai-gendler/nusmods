---
kind: edge
routes:
  web: Web
steps:
  - text: "The Student opens the Planner"
    kind: actor
    actor: student
    entities:
      - { entity: planner, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::planner" } }
  - text: "A planned course code cannot be loaded"
    kind: condition
    actor: student
    entities:
      - { entity: planned-course, effect: reads, facts: [Course] }
    contexts: { web: { place: "web::public::planner" } }
  - text: "The Product says it is unable to load the course, which may not exist"
    kind: product
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::planner" } }
---

# Course cannot be found

## Trigger

A planned code is not in the catalogue.

## Outcome

The student is told the course could not be loaded and may not exist.
