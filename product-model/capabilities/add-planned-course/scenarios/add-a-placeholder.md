---
kind: alternative
routes:
  web: Web
steps:
  - text: "The Student chooses Add Course in a semester and picks a placeholder such as Any GE module"
    kind: actor
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::planner" } }
  - text: "The Product adds the placeholder at the end of that semester"
    kind: product
    actor: student
    entities:
      - { entity: planned-course, effect: creates, facts: [Placeholder, Year, Semester, Position] }
    contexts: { web: { place: "web::public::planner" } }
---

# Add a placeholder

## Trigger

The student knows the kind of course but not which.

## Outcome

The placeholder holds the place, counting 4 units, until a course is chosen for it.
