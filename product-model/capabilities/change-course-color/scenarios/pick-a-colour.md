---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student opens the colour picker of a timetable course and picks a colour of their theme"
    kind: actor
    actor: student
    entities:
      - { entity: timetable-course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product draws the timetable course in that colour"
    kind: product
    actor: student
    entities:
      - { entity: timetable-course, effect: changes, facts: [Color] }
    contexts: { web: { place: "web::public::timetable" } }
---

# Pick a colour

## Trigger

The student wants a course in another colour.

## Outcome

The course's lessons and listing use the new colour.

## Edge cases

- A newly added course gets a colour no other course in the timetable has, while the theme has one left.
