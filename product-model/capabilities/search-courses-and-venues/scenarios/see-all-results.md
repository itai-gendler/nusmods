---
kind: alternative
routes:
  web: Web
steps:
  - text: "The Student types into the search box and chooses to see all courses or all venues"
    kind: actor
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [] }
      - { entity: venue, effect: reads, facts: [] }
    contexts: { web: { place: "web::public" } }
  - text: "The Product opens the course finder or the venues list searching for the same words"
    kind: product
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [] }
      - { entity: venue, effect: reads, facts: [] }
    contexts: { web: { place: "web::public" } }
---

# See all results

## Trigger

The student wants every match.

## Outcome

The student continues the search in the course finder or the venues list.
