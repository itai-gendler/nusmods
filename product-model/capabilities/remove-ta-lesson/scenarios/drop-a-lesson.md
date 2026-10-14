---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student picks a lesson of a timetable course in TA mode, then picks a chosen lesson again"
    kind: actor
    actor: student
    entities:
      - { entity: timetable-course, effect: reads, facts: [TA mode] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The timetable course has another chosen lesson"
    kind: condition
    actor: student
    entities:
      - { entity: timetable-course, effect: reads, facts: [Lessons chosen] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product removes the lesson from the timetable course's chosen lessons"
    kind: product
    actor: student
    entities:
      - { entity: timetable-course, effect: changes, facts: [Lessons chosen] }
    contexts: { web: { place: "web::public::timetable" } }
---

# Drop a lesson

## Trigger

The student no longer teaches one of the lessons.

## Outcome

The lesson is no longer among the course's chosen lessons.
