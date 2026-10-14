---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student chooses Enable TA on a timetable course"
    kind: actor
    actor: student
    entities:
      - { entity: timetable-course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product puts the timetable course in TA mode, keeping every lesson of the classes chosen so far"
    kind: product
    actor: student
    entities:
      - { entity: timetable-course, effect: changes, facts: [TA mode, Lessons chosen] }
      - { entity: course, effect: reads, facts: [Lessons] }
    contexts: { web: { place: "web::public::timetable" } }
---

# Teach a course

## Trigger

The student is a teaching assistant for a course in their timetable.

## Outcome

The course is in TA mode, keeping the lessons of the classes it had, and is left out of exam clashes and active units.
