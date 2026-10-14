---
kind: alternative
routes:
  web: Web
steps:
  - text: "The Student opens the Timetable"
    kind: actor
    actor: student
    entities:
      - { entity: timetable, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "At least one timetable course is hidden or in TA mode"
    kind: condition
    actor: student
    entities:
      - { entity: timetable-course, effect: reads, facts: [TA mode] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product shows the active units, leaving out hidden and TA mode courses, above the total units"
    kind: product
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [Units] }
      - { entity: timetable-course, effect: reads, facts: [TA mode] }
    contexts: { web: { place: "web::public::timetable" } }
---

# See active units

## Trigger

Some courses in the timetable are hidden or in TA mode.

## Outcome

The student sees both the active units and the total units.
