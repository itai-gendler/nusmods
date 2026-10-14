---
kind: alternative
routes:
  web: Web
steps:
  - text: "The Student chooses Add to Timetable on a planned course"
    kind: actor
    actor: student
    entities:
      - { entity: planned-course, effect: reads, facts: [Course, Semester] }
      - { entity: timetable, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::planner" } }
  - text: "The Product adds the course to the timetable of the semester it is planned in"
    kind: product
    actor: student
    entities:
      - { entity: timetable-course, effect: creates, to: Shown, facts: [Course, Lessons chosen, Color, TA mode] }
      - { entity: timetable, effect: reads, facts: [] }
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::planner" } }
---

# Add from the planner

## Trigger

The student planned a course for the current academic year and wants it in that semester's timetable.

## Outcome

The course is in that semester's timetable.

## Edge cases

- A planned course already in that timetable offers View in Timetable instead.
- Add to Timetable is offered only for semesters of the current academic year.
