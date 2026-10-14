---
kind: primary
result: achieved
routes:
  web: Web
steps:
  - text: "The Student chooses Random Course in the course finder"
    kind: actor
    actor: student
    capability: open-random-course
    entities:
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::course-finder" } }
  - text: "The Product opens the course page of a course matching the filters"
    kind: product
    actor: student
    capability: open-random-course
    entities:
      - { entity: course, effect: reads, facts: [Code] }
    contexts: { web: { place: "web::public::course-page" } }
  - text: "The Student chooses Add to and a semester"
    kind: actor
    actor: student
    capability: add-course-to-timetable
    entities: []
    contexts: { web: { place: "web::public::course-page" } }
  - text: "The Product adds the course to that semester's timetable"
    kind: product
    actor: student
    capability: add-course-to-timetable
    entities:
      - { entity: timetable-course, effect: creates, to: Shown, facts: [Course, Lessons chosen, Color, TA mode] }
      - { entity: timetable, effect: reads, facts: [] }
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::course-page" } }
---

# Add the random course

## Trigger

The student is browsing courses with no particular one in mind.

## Outcome

The course NUSMods picked is in a semester's timetable.
