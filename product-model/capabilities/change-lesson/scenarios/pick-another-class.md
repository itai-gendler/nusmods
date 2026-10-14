---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student picks a lesson of a timetable course on the timetable"
    kind: actor
    actor: student
    entities:
      - { entity: timetable-course, effect: reads, facts: [Lessons chosen] }
      - { entity: timetable, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product shows every class of that lesson type beside the chosen one"
    kind: product
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [Lessons] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Student picks another class"
    kind: actor
    actor: student
    entities: []
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product makes it the timetable course's chosen class of that lesson type"
    kind: product
    actor: student
    entities:
      - { entity: timetable-course, effect: changes, facts: [Lessons chosen] }
    contexts: { web: { place: "web::public::timetable" } }
---

# Pick another class

## Trigger

The student wants a different class of a lesson type.

## Outcome

The course has the new class of that lesson type in place of the old one.

## Edge cases

- A class with several lessons a week moves all of them together.
