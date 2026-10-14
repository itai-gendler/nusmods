---
kind: edge
routes:
  web: Web
steps:
  - text: "The Student opens the Timetable of a semester"
    kind: actor
    actor: student
    entities:
      - { entity: timetable, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The semester is not among those with exam dates available"
    kind: condition
    actor: student
    entities:
      - { entity: site-configuration, effect: reads, facts: [Exam dates available] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product warns that exam dates are not available for this semester yet and that course combinations may later conflict"
    kind: product
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
---

# Exam dates not yet published

## Trigger

The student opens a semester whose exam dates the university has not published.

## Outcome

The student is told exam dates are not available yet, and no exam information or exam calendar is offered.
