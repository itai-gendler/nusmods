---
kind: primary
routes:
  api: Public API
steps:
  - text: "The Developer requests the venue information of a semester"
    kind: actor
    actor: developer
    entities:
      - { entity: venue, effect: reads, facts: [] }
    contexts: { api: { place: public-api } }
  - text: "The Product returns each venue with its lessons and occupancy by day"
    kind: product
    actor: developer
    entities:
      - { entity: venue, effect: reads, facts: [Name, Lessons, Occupancy] }
    contexts: { api: { place: public-api } }
---

# Fetch the venues

## Trigger

A developer needs room availability.

## Outcome

The developer has every venue with its lessons and occupancy by day.
