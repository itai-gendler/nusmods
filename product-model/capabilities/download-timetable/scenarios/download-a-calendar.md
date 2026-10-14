---
kind: alternative
routes:
  web: Web
steps:
  - text: "The Student chooses Download, then iCalendar File (.ics)"
    kind: actor
    actor: student
    entities: []
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product makes an event for each shown course's lessons on the weeks they run, skipping holidays and recess, and one for each exam of a course not in TA mode, and downloads the file"
    kind: product
    actor: student
    entities:
      - { entity: timetable-course, effect: reads, facts: [Course, Lessons chosen, TA mode] }
      - { entity: course, effect: reads, facts: [Lessons, Exam] }
      - { entity: site-configuration, effect: reads, facts: [Holidays] }
    contexts: { web: { place: "web::public::timetable" } }
---

# Download a calendar

## Trigger

The student wants their lessons and exams in their own calendar.

## Outcome

The student has an iCalendar file of every lesson on its actual dates and every exam.

## Edge cases

- On a Mac the Product warns that the macOS Calendar app may show lessons during holidays and points to the FAQ.
- Hidden courses are left out of the calendar.
