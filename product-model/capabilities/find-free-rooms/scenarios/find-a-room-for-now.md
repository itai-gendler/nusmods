---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student chooses Find free rooms on Venues"
    kind: actor
    actor: student
    entities:
      - { entity: venue, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::venues" } }
  - text: "The Product sets the search to today, the current hour or the first class hour, for one hour"
    kind: product
    actor: student
    entities: []
    contexts: { web: { place: "web::public::venues" } }
  - text: "The Product lists the venues with no lesson in any half hour of that time"
    kind: product
    actor: student
    entities:
      - { entity: venue, effect: reads, facts: [Name, Room name, Occupancy] }
    contexts: { web: { place: "web::public::venues" } }
---

# Find a room for now

## Trigger

The student needs somewhere to study.

## Outcome

The student sees the rooms free for the chosen hours, starting from the current hour.
