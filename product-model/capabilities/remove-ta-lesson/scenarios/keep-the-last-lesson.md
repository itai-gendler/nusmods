---
kind: validation
routes:
  web: Web
steps:
  - text: "The Student picks a lesson of a timetable course in TA mode, then picks a chosen lesson again"
    kind: actor
    actor: student
    entities:
      - { entity: timetable-course, effect: reads, facts: [TA mode] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "It is the timetable course's last chosen lesson"
    kind: condition
    actor: student
    entities:
      - { entity: timetable-course, effect: reads, facts: [Lessons chosen] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product keeps the lesson and stops showing the other lessons"
    kind: product
    actor: student
    entities: []
    contexts: { web: { place: "web::public::timetable" } }
---

# Keep the last lesson

## Trigger

The student picks the only lesson a course in TA mode has left.

## Outcome

The lesson stays; the course keeps at least one lesson.
