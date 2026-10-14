---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student chooses Export on the Planner"
    kind: actor
    actor: student
    entities:
      - { entity: planner, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::planner" } }
  - text: "The Product downloads the plan as a file"
    kind: product
    actor: student
    entities:
      - { entity: planner, effect: reads, facts: [Matriculation year, Graduation year, iBLOCs, Ignore prerequisite checking, Custom course details] }
      - { entity: planned-course, effect: reads, facts: [Course, Placeholder, Year, Semester, Position] }
    contexts: { web: { place: "web::public::planner" } }
---

# Download the plan

## Trigger

The student wants a copy of the plan or to move it to another device.

## Outcome

The student has a planner file.
