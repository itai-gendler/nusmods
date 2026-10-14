---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student opens a placeholder and picks one of the courses it allows"
    kind: actor
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::planner" } }
  - text: "The Product sets the planned course to that course and loads its details"
    kind: product
    actor: student
    entities:
      - { entity: planned-course, effect: changes, facts: [Course] }
      - { entity: course, effect: reads, facts: [Code, Title, Units] }
    contexts: { web: { place: "web::public::planner" } }
---

# Pick a course

## Trigger

The student decides which course fills a placeholder.

## Outcome

The placeholder becomes that course.
