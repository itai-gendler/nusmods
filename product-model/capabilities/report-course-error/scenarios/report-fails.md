---
kind: edge
routes:
  web: Web
steps:
  - text: "The Student sends a course error report"
    kind: actor
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::course-page" } }
  - text: "The report service does not accept it"
    kind: condition
    actor: student
    entities: []
    contexts: { web: { place: "web::public::course-page" } }
  - text: "The Product says the report could not be sent"
    kind: product
    actor: student
    entities: []
    contexts: { web: { place: "web::public::course-page" } }
---

# Report fails

## Trigger

The report cannot be sent.

## Outcome

The student is told it failed and can try again.
