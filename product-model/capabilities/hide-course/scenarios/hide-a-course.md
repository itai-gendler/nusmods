---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student chooses Hide on a timetable course"
    kind: actor
    actor: student
    entities:
      - { entity: timetable-course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product hides the timetable course"
    kind: product
    actor: student
    entities:
      - { entity: timetable-course, effect: changes, from: Shown, to: Hidden, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
---

# Hide a course

## Trigger

The student wants a course out of the way without removing it.

## Outcome

The course stays listed, greyed, but its lessons leave the timetable, the Today page and exam clashes.

## Edge cases

- A hidden course still counts towards total units but not active units.
