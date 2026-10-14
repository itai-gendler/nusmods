---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student chooses Show on a hidden timetable course"
    kind: actor
    actor: student
    entities:
      - { entity: timetable-course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product shows the timetable course again"
    kind: product
    actor: student
    entities:
      - { entity: timetable-course, effect: changes, from: Hidden, to: Shown, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
---

# Show a hidden course

## Trigger

The student wants a hidden course back on the timetable.

## Outcome

The course's lessons show again with the classes chosen before it was hidden.
