---
kind: alternative
routes:
  web: Web
steps:
  - text: "The Student chooses Optimise"
    kind: actor
    actor: student
    entities: []
    contexts: { web: { place: "web::public::optimiser" } }
  - text: "Some lesson types have no class that fits the free days and hours"
    kind: condition
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [Lessons] }
    contexts: { web: { place: "web::public::optimiser" } }
  - text: "The Product says a partial timetable was generated, lists the lessons it could not schedule with reasons, and offers the timetable without them or with default classes"
    kind: product
    actor: student
    entities:
      - { entity: timetable, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::optimiser" } }
---

# Partial timetable

## Trigger

Some lessons cannot be scheduled within the preferences.

## Outcome

The student is told which lessons could not be scheduled and why, and can open the timetable without them or with default classes for them.
