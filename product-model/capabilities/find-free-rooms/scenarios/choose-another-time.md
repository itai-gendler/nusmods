---
kind: alternative
routes:
  web: Web
steps:
  - text: "The Student changes the day, start time or duration"
    kind: actor
    actor: student
    entities: []
    contexts: { web: { place: "web::public::venues" } }
  - text: "The Product keeps the duration within school hours and lists the venues free for the whole time"
    kind: product
    actor: student
    entities:
      - { entity: venue, effect: reads, facts: [Name, Occupancy] }
    contexts: { web: { place: "web::public::venues" } }
---

# Choose another time

## Trigger

The student plans for later.

## Outcome

The rooms free for the chosen day, start and duration are listed.
