---
kind: edge
routes:
  web: Web
steps:
  - text: "The Student opens a course page while offline"
    kind: actor
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::course-page" } }
  - text: "The student is offline"
    kind: condition
    actor: student
    entities: []
    contexts: { web: { place: "web::public::course-page" } }
  - text: "The Product says comments are not available while offline"
    kind: product
    actor: student
    entities: []
    contexts: { web: { place: "web::public::course-page" } }
---

# Reviews while offline

## Trigger

The student opens a course page offline.

## Outcome

The course details show, and the reviews section says comments are not available offline.
