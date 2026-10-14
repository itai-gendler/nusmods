---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student chooses Add Course in a semester and types one or more course codes"
    kind: actor
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::planner" } }
  - text: "The Product adds each code found in what was typed at the end of that semester and loads its details"
    kind: product
    actor: student
    entities:
      - { entity: planned-course, effect: creates, facts: [Course, Year, Semester, Position] }
      - { entity: course, effect: reads, facts: [Code, Title, Units] }
    contexts: { web: { place: "web::public::planner" } }
---

# Add a course to a semester

## Trigger

The student plans to take a course in a semester.

## Outcome

The course is at the end of that semester in the plan.

## Edge cases

- Exemptions, Plan to Take and, with iBLOCs on, the iBLOCs list take courses the same way.
