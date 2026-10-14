---
kind: edge
routes:
  web: Web
steps:
  - text: "The Student opens Courses"
    kind: actor
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::course-finder" } }
  - text: "The search service does not answer"
    kind: condition
    actor: student
    entities: []
    contexts: { web: { place: "web::public::course-finder" } }
  - text: "The Product says the courses could not be loaded and offers to retry"
    kind: product
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::course-finder" } }
---

# Search unavailable

## Trigger

The search service cannot be reached.

## Outcome

The student is told courses cannot be loaded and can try again.
