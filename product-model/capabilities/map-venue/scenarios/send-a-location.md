---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student chooses Help us improve this map or Help us map this venue on a venue"
    kind: actor
    actor: student
    entities:
      - { entity: venue, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::venue" } }
  - text: "The Product shows a map at the venue's known place and floor, or the campus"
    kind: product
    actor: student
    entities:
      - { entity: venue, effect: reads, facts: [Room name, Floor, Location] }
    contexts: { web: { place: "web::public::venue" } }
  - text: "The Student enters the room name and floor, places the venue on the map and optionally their email, and submits"
    kind: actor
    actor: student
    entities:
      - { entity: venue, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::venue" } }
  - text: "The Product sends the suggestion with the venue code, room name, floor and place to the NUSMods team"
    kind: product
    actor: student
    entities:
      - { entity: venue, effect: reads, facts: [Name] }
    contexts: { web: { place: "web::public::venue" } }
---

# Send a location

## Trigger

The student knows where a venue is.

## Outcome

The NUSMods team receives the suggestion to review.
