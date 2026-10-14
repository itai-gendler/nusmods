---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student picks a lesson of a timetable course in TA mode"
    kind: actor
    actor: student
    entities:
      - { entity: timetable-course, effect: reads, facts: [TA mode] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product shows every lesson of that course that can be added"
    kind: product
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [Lessons] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Student picks a lesson not yet chosen"
    kind: actor
    actor: student
    entities: []
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product adds the lesson to the timetable course's chosen lessons"
    kind: product
    actor: student
    entities:
      - { entity: timetable-course, effect: changes, facts: [Lessons chosen] }
    contexts: { web: { place: "web::public::timetable" } }
---

# Add another lesson

## Trigger

The student teaches one more lesson of a course.

## Outcome

The lesson is among the course's chosen lessons, beside the others of its type.
