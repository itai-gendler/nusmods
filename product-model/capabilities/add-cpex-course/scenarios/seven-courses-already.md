---
kind: validation
routes:
  web: Web
steps:
  - text: "The Student looks to add another course"
    kind: actor
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::signed-in::cpex-response" } }
  - text: "The Student has seven CPEx courses"
    kind: condition
    actor: student
    entities:
      - { entity: cpex-course, effect: reads, facts: [Course] }
    contexts: { web: { place: "web::signed-in::cpex-response" } }
  - text: "The Product says the maximum of seven courses is selected and to remove one to add more"
    kind: product
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::signed-in::cpex-response" } }
---

# Seven courses already

## Trigger

The response already has seven courses.

## Outcome

No course can be added until one is removed.

## Edge cases

- A course already in the response is not added again.
