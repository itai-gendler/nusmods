---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student types into the search box, or presses / to reach it"
    kind: actor
    actor: student
    entities: []
    contexts: { web: { place: "web::public" } }
  - text: "The Product lists up to ten courses and venues matching every word typed, courses by code or title"
    kind: product
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [Code, Title] }
      - { entity: venue, effect: reads, facts: [Name] }
    contexts: { web: { place: "web::public" } }
  - text: "The Student picks a course or venue"
    kind: actor
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [] }
      - { entity: venue, effect: reads, facts: [] }
    contexts: { web: { place: "web::public" } }
  - text: "The Product opens its page"
    kind: product
    actor: student
    entities: []
    contexts: { web: { place: "web::public" } }
---

# Go to a result

## Trigger

The student knows roughly which course or venue they want.

## Outcome

The student is on the page of the course or venue they picked.

## Edge cases

- Where both match plentifully, six courses and four venues are listed.
