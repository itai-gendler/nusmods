---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student chooses Reset on the Planner"
    kind: actor
    actor: student
    entities:
      - { entity: planner, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::planner" } }
  - text: "The Product asks whether to permanently reset all courses and settings"
    kind: product
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::planner" } }
  - text: "The Student confirms"
    kind: actor
    actor: student
    entities: []
    contexts: { web: { place: "web::public::planner" } }
  - text: "The Product removes every planned course and sets the years to the current academic year, iBLOCs off and prerequisite checking on"
    kind: product
    actor: student
    entities:
      - { entity: planned-course, effect: removes }
      - { entity: planner, effect: changes, facts: [Matriculation year, Graduation year, iBLOCs, Ignore prerequisite checking, Custom course details] }
    contexts: { web: { place: "web::public::planner" } }
---

# Start the plan over

## Trigger

The student wants a fresh plan.

## Outcome

The plan is empty, starting and ending in the current academic year.
