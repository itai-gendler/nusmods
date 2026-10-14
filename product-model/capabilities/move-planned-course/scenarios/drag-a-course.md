---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student drags a planned course to a place in a semester or list"
    kind: actor
    actor: student
    entities:
      - { entity: planned-course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::planner" } }
  - text: "The Product moves the planned course there and renumbers the courses of the semesters it left and joined"
    kind: product
    actor: student
    entities:
      - { entity: planned-course, effect: changes, facts: [Year, Semester, Position] }
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::planner" } }
---

# Drag a course

## Trigger

The student changes when they will take a course.

## Outcome

The course sits where it was dropped and the other courses close up around it.
