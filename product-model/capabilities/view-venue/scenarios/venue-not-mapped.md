---
kind: edge
routes:
  web: Web
steps:
  - text: "The Student opens a venue"
    kind: actor
    actor: student
    entities:
      - { entity: venue, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::venue" } }
  - text: "The venue has no known location"
    kind: condition
    actor: student
    entities:
      - { entity: venue, effect: reads, facts: [Location] }
    contexts: { web: { place: "web::public::venue" } }
  - text: "The Product says it does not have the location of this venue and offers Help us map this venue"
    kind: product
    actor: student
    entities:
      - { entity: venue, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::venue" } }
---

# Venue not mapped

## Trigger

NUSMods has no location for the venue.

## Outcome

The student is told NUSMods does not know where it is and is invited to help map it.
