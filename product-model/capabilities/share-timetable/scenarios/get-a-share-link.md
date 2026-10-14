---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student chooses Share/Sync on the Timetable"
    kind: actor
    actor: student
    entities:
      - { entity: timetable, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product makes a link holding the semester and each timetable course with its chosen lessons, hidden and TA mode courses marked, and shows it with a QR code"
    kind: product
    actor: student
    entities:
      - { entity: timetable, effect: reads, facts: [Semester] }
      - { entity: timetable-course, effect: reads, facts: [Course, Lessons chosen, TA mode] }
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Student copies the link or chooses Send Email, WhatsApp or Telegram"
    kind: actor
    actor: student
    entities: []
    contexts: { web: { place: "web::public::timetable" } }
---

# Get a share link

## Trigger

The student wants to share or sync their timetable.

## Outcome

The student has a link and QR code that open their timetable, and can copy it or send it by email, WhatsApp or Telegram.

## Edge cases

- Where copying is not possible the Product asks the student to press Cmd/Ctrl + C.
