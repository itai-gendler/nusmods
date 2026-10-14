---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student picks an earlier academic year on a course page"
    kind: actor
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::course-page" } }
  - text: "The Product shows the course as it was that academic year with a warning that the information may be out of date"
    kind: product
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [Code, Title, Description, Units, Semesters offered, Prerequisite, Prerequisite tree, Exam, Lessons, Academic year] }
    contexts: { web: { place: "web::public::course-archive" } }
---

# Read an earlier year

## Trigger

The student wants to know how a course ran before.

## Outcome

The student sees the course as it was that year, marked as archived.

## Edge cases

- Archives go back to 2016/2017.
- An archived page offers no adding to a timetable or the planner.
