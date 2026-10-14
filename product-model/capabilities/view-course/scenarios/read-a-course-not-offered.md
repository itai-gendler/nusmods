---
kind: alternative
routes:
  web: Web
steps:
  - text: "The Student opens a course page"
    kind: actor
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::course-page" } }
  - text: "The course is not offered this academic year"
    kind: condition
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [Semesters offered] }
    contexts: { web: { place: "web::public::course-page" } }
  - text: "The Product says the course is not offered this academic year and may be used to map exchange courses"
    kind: product
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::course-page" } }
---

# Read a course not offered this year

## Trigger

The student opens a course offered in no semester this year.

## Outcome

The student sees the course with a notice that it is not offered this academic year, and cannot add it to a timetable or the planner from here.
