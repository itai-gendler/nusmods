---
kind: edge
routes:
  web: Web
steps:
  - text: "The Student chooses Random Course in the course finder"
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
  - text: "The Product says it failed to fetch a random course"
    kind: product
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::course-finder" } }
---

# No random course

## Trigger

A random course cannot be fetched.

## Outcome

The student stays in the course finder and is told it failed.
