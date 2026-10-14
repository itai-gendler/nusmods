---
kind: alternative
routes:
  web: Web
steps:
  - text: "The Student chooses to add a planned semester of the current academic year to its timetable"
    kind: actor
    actor: student
    entities:
      - { entity: planned-course, effect: reads, facts: [Course, Semester] }
      - { entity: timetable, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::planner" } }
  - text: "The Product adds each planned course not yet in that timetable"
    kind: product
    actor: student
    entities:
      - { entity: timetable-course, effect: creates, to: Shown, facts: [Course, Lessons chosen, Color, TA mode] }
      - { entity: planned-course, effect: reads, facts: [] }
      - { entity: timetable, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::planner" } }
---

# Add a planned semester

## Trigger

The student has planned a semester of the current academic year and wants it all in the timetable.

## Outcome

Every course planned for that semester is in its timetable.
