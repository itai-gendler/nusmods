---
kind: primary
routes:
  web: Web
steps:
  - text: "The Product shows the next or current CourseReg round for the student's course type, with when it starts or ends"
    kind: product
    actor: student
    entities:
      - { entity: site-configuration, effect: reads, facts: [CourseReg schedule] }
      - { entity: student, effect: reads, facts: [Course type, CourseReg reminders] }
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Student closes the reminder"
    kind: actor
    actor: student
    entities: []
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product records the round as dismissed"
    kind: product
    actor: student
    entities:
      - { entity: student, effect: changes, facts: [Dismissed reminders] }
    contexts: { web: { place: "web::public::timetable" } }
---

# Close a reminder

## Trigger

The student no longer wants to see a CourseReg round's reminder.

## Outcome

That round's reminder no longer shows for the rest of the semester; it can be turned back on in Settings.
