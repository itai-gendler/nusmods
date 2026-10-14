---
kind: alternative
routes:
  web: Web
steps:
  - text: "The Student turns CourseReg reminders on or off, chooses Undergraduate or Graduate, and turns individual rounds' reminders on or off"
    kind: actor
    actor: student
    entities: []
    contexts: { web: { place: "web::public::settings" } }
  - text: "The Product keeps the choices and previews the next reminder"
    kind: product
    actor: student
    entities:
      - { entity: student, effect: changes, facts: [CourseReg reminders, Course type, Dismissed reminders] }
      - { entity: site-configuration, effect: reads, facts: [CourseReg schedule] }
    contexts: { web: { place: "web::public::settings" } }
---

# Change CourseReg reminders

## Trigger

The student wants CourseReg reminders for their course type, or none.

## Outcome

The Timetable shows reminders of the chosen course type's rounds, or none.

## Edge cases

- The course type also decides which programme-type requisites the planner checks.
