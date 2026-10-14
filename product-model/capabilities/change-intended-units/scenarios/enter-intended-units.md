---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student enters the intended number of units"
    kind: actor
    actor: student
    entities: []
    contexts: { web: { place: "web::signed-in::cpex-response" } }
  - text: "The Product keeps the number and saves the response"
    kind: product
    actor: student
    entities:
      - { entity: cpex-submission, effect: changes, facts: [Intended units] }
    contexts: { web: { place: "web::signed-in::cpex-response" } }
---

# Enter intended units

## Trigger

The student plans their load.

## Outcome

The response carries the intended units and is saved.

## Edge cases

- The intended units do not limit how many courses can be selected.
