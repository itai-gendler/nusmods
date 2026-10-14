---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student types a course code or title into \"Add course to timetable\""
    kind: actor
    actor: student
    entities:
      - { entity: timetable, effect: reads, facts: [] }
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product lists matching courses offered in the semester, marking those already added"
    kind: product
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [Code, Title, Semesters offered] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Student picks a course"
    kind: actor
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product adds the course to the timetable with a random class of each lesson type and a colour not yet used"
    kind: product
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [Lessons] }
      - { entity: timetable-course, effect: creates, to: Shown, facts: [Course, Lessons chosen, Color, TA mode] }
      - { entity: timetable, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
---

# Add from the timetable

## Trigger

The student wants to take a course this semester.

## Outcome

The course is in the timetable with one class of each lesson type and its own colour.

## Edge cases

- Courses already in the timetable are listed but cannot be picked again; they offer Remove instead.
