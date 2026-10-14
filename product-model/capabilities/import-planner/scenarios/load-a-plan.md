---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student chooses Import on the Planner and picks a planner file"
    kind: actor
    actor: student
    entities:
      - { entity: planner, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::planner" } }
  - text: "The Product checks the file and replaces the whole plan and its settings with it, loading each course's details"
    kind: product
    actor: student
    entities:
      - { entity: planned-course, as: old, effect: removes }
      - { entity: planned-course, as: imported, effect: creates, facts: [Course, Placeholder, Year, Semester, Position] }
      - { entity: planner, effect: changes, facts: [Matriculation year, Graduation year, iBLOCs, Ignore prerequisite checking, Custom course details] }
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::planner" } }
  - text: "The Product says the plan was imported successfully"
    kind: product
    actor: student
    entities: []
    contexts: { web: { place: "web::public::planner" } }
---

# Load a plan

## Trigger

The student has a planner file.

## Outcome

The plan in the file replaces the student's plan.
