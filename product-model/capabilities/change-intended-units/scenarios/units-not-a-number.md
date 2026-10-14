---
kind: validation
routes:
  web: Web
steps:
  - text: "The Student enters something that is not a number"
    kind: actor
    actor: student
    entities: []
    contexts: { web: { place: "web::signed-in::cpex-response" } }
  - text: "The Product keeps the previous intended units and shows them again"
    kind: product
    actor: student
    entities:
      - { entity: cpex-submission, effect: reads, facts: [Intended units] }
    contexts: { web: { place: "web::signed-in::cpex-response" } }
---

# Units not a number

## Trigger

The student enters something that is not a number of units.

## Outcome

The intended units stay as they were.
