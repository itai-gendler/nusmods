---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student opens the Optimiser"
    kind: actor
    actor: student
    entities: []
    contexts: { web: { place: "web::public::optimiser" } }
  - text: "The Product lists the lesson types of the current semester's timetable courses"
    kind: product
    actor: student
    entities:
      - { entity: timetable-course, effect: reads, facts: [Course, Lessons chosen] }
      - { entity: course, effect: reads, facts: [Lessons] }
    contexts: { web: { place: "web::public::optimiser" } }
  - text: "The Student chooses lessons they will attend by recording, free days, earliest and latest lesson times, lunch hours, the most consecutive hours and classes to pin, and chooses Optimise"
    kind: actor
    actor: student
    entities: []
    contexts: { web: { place: "web::public::optimiser" } }
  - text: "The Product searches the class combinations for the one that best meets the preferences, never putting a physical lesson on a free day or outside the chosen hours"
    kind: product
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [Lessons] }
      - { entity: venue, effect: reads, facts: [Location] }
    contexts: { web: { place: "web::public::optimiser" } }
  - text: "The Product says the optimised timetable is ready and offers Open Optimised Timetable"
    kind: product
    actor: student
    entities:
      - { entity: timetable, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::optimiser" } }
---

# Get an optimised timetable

## Trigger

The student wants a timetable that suits them.

## Outcome

The student has a link to an optimised timetable they can open and import.
