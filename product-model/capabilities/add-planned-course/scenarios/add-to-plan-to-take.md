---
kind: alternative
routes:
  web: Web
steps:
  - text: "The Student chooses to add the course to their Plan to Take list on its course page"
    kind: actor
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::course-page" } }
  - text: "The Product adds the course to the Plan to Take list"
    kind: product
    actor: student
    entities:
      - { entity: planned-course, effect: creates, facts: [Course, Year, Semester, Position] }
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::course-page" } }
---

# Add to Plan to Take

## Trigger

The student is reading a course they may take some day.

## Outcome

The course is in the planner's Plan to Take list and the button offers to remove it.
