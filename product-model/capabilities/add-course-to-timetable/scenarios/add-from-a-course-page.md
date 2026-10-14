---
kind: alternative
routes:
  web: Web
steps:
  - text: "The Student chooses Add to and a semester the course is offered in, on its course page"
    kind: actor
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [Semesters offered] }
    contexts: { web: { place: "web::public::course-page" } }
  - text: "The Product adds the course to that semester's timetable with a random class of each lesson type"
    kind: product
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [Lessons] }
      - { entity: timetable-course, effect: creates, to: Shown, facts: [Course, Lessons chosen, Color, TA mode] }
      - { entity: timetable, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::course-page" } }
---

# Add from a course page

## Trigger

The student is reading a course they want to take.

## Outcome

The course is in the chosen semester's timetable and the button offers to remove it.

## Edge cases

- The button is not offered on archived pages or for courses not offered this year.
