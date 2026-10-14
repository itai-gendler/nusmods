---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student chooses Edit Unit and Title on a planned course"
    kind: actor
    actor: student
    entities:
      - { entity: planned-course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::planner" } }
  - text: "The Product fills in the units and title it has for the code"
    kind: product
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [Units, Title] }
    contexts: { web: { place: "web::public::planner" } }
  - text: "The Student enters units and, optionally, a title, and saves"
    kind: actor
    actor: student
    entities: []
    contexts: { web: { place: "web::public::planner" } }
  - text: "The Product keeps them for the course code"
    kind: product
    actor: student
    entities:
      - { entity: planner, effect: changes, facts: [Custom course details] }
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::planner" } }
---

# Enter units and title

## Trigger

The student's course has no information in NUSMods, or it is wrong for them.

## Outcome

The plan uses the entered units and title for that code everywhere it appears.
