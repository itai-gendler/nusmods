---
kind: edge
routes:
  web: Web
steps:
  - text: "The Student chooses Optimise"
    kind: actor
    actor: student
    entities: []
    contexts: { web: { place: "web::public::optimiser" } }
  - text: "The optimiser does not answer or fails"
    kind: condition
    actor: student
    entities: []
    contexts: { web: { place: "web::public::optimiser" } }
  - text: "The Product shows that the request failed"
    kind: product
    actor: student
    entities: []
    contexts: { web: { place: "web::public::optimiser" } }
---

# Optimiser unavailable

## Trigger

The optimiser fails.

## Outcome

The student sees an error and can try again.
