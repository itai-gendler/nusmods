---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student opens the Timetable"
    kind: actor
    actor: student
    entities:
      - { entity: timetable, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product opens the timetable of the semester NUSMods is on and puts right any chosen classes the latest course data no longer has"
    kind: product
    actor: student
    entities:
      - { entity: site-configuration, effect: reads, facts: [Current semester] }
      - { entity: timetable, effect: reads, facts: [Semester] }
      - { entity: timetable-course, effect: changes, facts: [Lessons chosen] }
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product draws the chosen lessons of each shown timetable course on the week grid, in its colour, overlapping lessons on extra rows"
    kind: product
    actor: student
    entities:
      - { entity: timetable-course, effect: reads, facts: [Course, Lessons chosen, Color] }
      - { entity: course, effect: reads, facts: [Lessons] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product lists every timetable course with its code, title, exam date and duration and units, in exam date order, and the total units"
    kind: product
    actor: student
    entities:
      - { entity: timetable-course, effect: reads, facts: [Course] }
      - { entity: course, effect: reads, facts: [Code, Title, Exam, Units] }
    contexts: { web: { place: "web::public::timetable" } }
---

# See a semester timetable

## Trigger

The student opens the Timetable.

## Outcome

The student sees the semester's lessons on the week grid and the list of its courses with exams and units.

## Edge cases

- A semester with no courses says "No courses added."
- Courses can be listed by exam date, units or course code instead.
- Lessons on Saturday and Sunday show when a course has them.
