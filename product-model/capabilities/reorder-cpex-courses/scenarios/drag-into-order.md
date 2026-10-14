---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student drags a CPEx course to another place in the list"
    kind: actor
    actor: student
    entities:
      - { entity: cpex-course, effect: reads, facts: [] }
    contexts: { web: { place: "web::signed-in::cpex-response" } }
  - text: "The Product ranks the courses in the new order and saves the response"
    kind: product
    actor: student
    entities:
      - { entity: cpex-course, effect: changes, facts: [Rank] }
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::signed-in::cpex-response" } }
---

# Drag into order

## Trigger

The student prefers one course over another.

## Outcome

The courses are ranked in the new order and the response is saved.
