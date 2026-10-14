---
kind: edge
routes:
  web: Web
steps:
  - text: "The Student chooses Export on the Planner"
    kind: actor
    actor: student
    entities:
      - { entity: planner, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::planner" } }
  - text: "The saved plan does not have the expected shape"
    kind: condition
    actor: student
    entities: []
    contexts: { web: { place: "web::public::planner" } }
  - text: "The Product says the planner data is corrupted"
    kind: product
    actor: student
    entities:
      - { entity: planner, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::planner" } }
---

# Plan cannot be exported

## Trigger

The saved plan is not in a shape NUSMods can export.

## Outcome

Nothing is downloaded and the student is told the planner data is corrupted.
