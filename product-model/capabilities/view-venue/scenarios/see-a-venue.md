---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student picks a venue"
    kind: actor
    actor: student
    entities:
      - { entity: venue, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::venues" } }
  - text: "The Product shows the room name and floor, its place on the campus map with nearby bus stops, and its lessons through the week"
    kind: product
    actor: student
    entities:
      - { entity: venue, effect: reads, facts: [Name, Room name, Floor, Location, Lessons] }
    contexts: { web: { place: "web::public::venue" } }
---

# See a venue

## Trigger

The student picks a venue.

## Outcome

The student sees the room's name, floor, place on the map and weekly timetable.

## Edge cases

- The venues before and after it in order can be reached from its page.
