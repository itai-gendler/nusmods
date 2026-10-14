---
kind: alternative
routes:
  web: Web
steps:
  - text: "The Student opens the Planner"
    kind: actor
    actor: student
    entities:
      - { entity: planner, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::planner" } }
  - text: "The Product checks each planned course against the courses planned in earlier semesters and exemptions, its semesters offered, the exams of its semester in the current academic year, the rest of its semester and the catalogue"
    kind: product
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [Prerequisite tree, Semesters offered, Exam] }
      - { entity: planner, effect: reads, facts: [Matriculation year, Ignore prerequisite checking] }
      - { entity: student, effect: reads, facts: [Course type] }
      - { entity: planned-course, effect: changes, facts: [Warnings] }
    contexts: { web: { place: "web::public::planner" } }
  - text: "The Product marks each course with a problem and says which prerequisites are unmet, which semesters it is offered in, which courses clash, that it is a duplicate, or that no information was found"
    kind: product
    actor: student
    entities:
      - { entity: planned-course, effect: reads, facts: [Warnings] }
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::planner" } }
---

# See planner warnings

## Trigger

Some planned courses have problems.

## Outcome

Each such course carries a warning saying what is wrong.

## Edge cases

- With Ignore prerequisite checking on, no prerequisite warnings show.
