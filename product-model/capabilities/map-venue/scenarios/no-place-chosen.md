---
kind: validation
routes:
  web: Web
steps:
  - text: "The Student submits a venue suggestion without choosing a place on the map"
    kind: actor
    actor: student
    entities:
      - { entity: venue, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::venue" } }
  - text: "The Product asks the student to choose the location on the map"
    kind: product
    actor: student
    entities: []
    contexts: { web: { place: "web::public::venue" } }
---

# No place chosen

## Trigger

The student submits without moving the venue on the map.

## Outcome

Nothing is sent until the student places the venue.
