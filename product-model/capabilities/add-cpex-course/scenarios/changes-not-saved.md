---
kind: edge
routes:
  web: Web
steps:
  - text: "The Student adds a CPEx course"
    kind: actor
    actor: student
    entities:
      - { entity: cpex-course, effect: reads, facts: [] }
    contexts: { web: { place: "web::signed-in::cpex-response" } }
  - text: "The university does not accept the save"
    kind: condition
    actor: student
    entities: []
    contexts: { web: { place: "web::signed-in::cpex-response" } }
  - text: "The Product says the changes could not be saved and offers Retry Saving Changes"
    kind: product
    actor: student
    entities: []
    contexts: { web: { place: "web::signed-in::cpex-response" } }
---

# Changes not saved

## Trigger

The response cannot be saved.

## Outcome

The student is told the changes could not be saved and can retry.
