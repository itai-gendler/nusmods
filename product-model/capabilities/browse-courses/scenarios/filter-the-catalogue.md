---
kind: alternative
routes:
  web: Web
steps:
  - text: "The Student ticks filters for semester offered, level, units, faculty, department, grading basis or other attributes"
    kind: actor
    actor: student
    entities: []
    contexts: { web: { place: "web::public::course-finder" } }
  - text: "The Product lists only the courses matching the filters, showing how many each option would give"
    kind: product
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [Semesters offered, Units, Faculty, Department, Code] }
    contexts: { web: { place: "web::public::course-finder" } }
---

# Filter the catalogue

## Trigger

The student wants courses that fit set criteria.

## Outcome

Only courses meeting every chosen filter are listed.

## Edge cases

- Courses opens filtered to every semester.
