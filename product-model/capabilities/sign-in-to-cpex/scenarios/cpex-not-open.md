---
kind: edge
routes:
  web: Web
steps:
  - text: "The Student opens CPEx"
    kind: actor
    actor: student
    entities: []
    contexts: { web: { place: "web::public::cpex" } }
  - text: "The Course Planning Exercise is not open"
    kind: condition
    actor: student
    entities:
      - { entity: site-configuration, effect: reads, facts: [CPEx open] }
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::cpex" } }
  - text: "The Product shows when undergraduate and graduate CPEx open, or that they have ended"
    kind: product
    actor: student
    entities:
      - { entity: site-configuration, effect: reads, facts: [CPEx round] }
    contexts: { web: { place: "web::public::cpex" } }
---

# CPEx not open

## Trigger

The exercise is not taking responses.

## Outcome

The student sees when the exercise opens, or that it has ended, and cannot sign in.
