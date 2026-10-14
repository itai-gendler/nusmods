---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student opens Venues and types a search"
    kind: actor
    actor: student
    entities:
      - { entity: venue, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::venues" } }
  - text: "The Product lists the venues whose code or room name contains every word, in order of code"
    kind: product
    actor: student
    entities:
      - { entity: venue, effect: reads, facts: [Name, Room name] }
    contexts: { web: { place: "web::public::venues" } }
---

# Search venues

## Trigger

The student looks for a room.

## Outcome

The student sees the venues whose code or room name contains every word typed.
