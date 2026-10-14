---
kind: alternative
routes:
  web: Web
steps:
  - text: "The Student opens Today"
    kind: actor
    actor: student
    entities: []
    contexts: { web: { place: "web::public::today" } }
  - text: "Today has no lessons, or every lesson has ended"
    kind: condition
    actor: student
    entities:
      - { entity: timetable-course, effect: reads, facts: [Lessons chosen] }
    contexts: { web: { place: "web::public::today" } }
  - text: "The Product says \"You have no lessons today\" or \"You have no lessons left today\""
    kind: product
    actor: student
    entities: []
    contexts: { web: { place: "web::public::today" } }
---

# No lessons left

## Trigger

The student has no lessons today, or none left.

## Outcome

The student is told they have no lessons today, or none left today.
