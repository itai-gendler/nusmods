---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student chooses Exam Calendar on the Timetable"
    kind: actor
    actor: student
    entities:
      - { entity: timetable, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The semester has exam dates available"
    kind: condition
    actor: student
    entities:
      - { entity: site-configuration, effect: reads, facts: [Exam dates available] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product shows the exam weeks with each timetable course's exam on its day and time, in the course's colour"
    kind: product
    actor: student
    entities:
      - { entity: timetable-course, effect: reads, facts: [Course, Color] }
      - { entity: course, effect: reads, facts: [Code, Exam] }
    contexts: { web: { place: "web::public::timetable" } }
---

# See exams on a calendar

## Trigger

The student wants to see when their exams fall.

## Outcome

The student sees each course's exam on the day and time it is held; choosing Timetable returns to the lesson grid.

## Edge cases

- Courses without an exam are not on the calendar.
