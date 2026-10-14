---
kind: alternative
routes:
  web: Web
steps:
  - text: "The Student chooses Remove from and the semester on the course page"
    kind: actor
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::course-page" } }
  - text: "The Product removes the course from that semester's timetable"
    kind: product
    actor: student
    entities:
      - { entity: timetable-course, effect: removes, from: Shown }
      - { entity: timetable, effect: reads, facts: [] }
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::course-page" } }
---

# Remove from a course page

## Trigger

The student is on the page of a course already in a timetable.

## Outcome

The course leaves that semester's timetable.
