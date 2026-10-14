---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student chooses Remove on a planned course, or drags it to the bin"
    kind: actor
    actor: student
    entities:
      - { entity: planned-course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::planner" } }
  - text: "The Product removes the planned course"
    kind: product
    actor: student
    entities:
      - { entity: planned-course, effect: removes }
    contexts: { web: { place: "web::public::planner" } }
---

# Remove from the plan

## Trigger

The student no longer plans to take a course.

## Outcome

The course is gone from the plan.
