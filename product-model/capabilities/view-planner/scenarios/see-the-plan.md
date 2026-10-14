---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student opens the Planner"
    kind: actor
    actor: student
    entities:
      - { entity: planner, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::planner" } }
  - text: "The Product lays out each academic year from matriculation to graduation with its semesters, and the Exemptions and Plan to Take lists"
    kind: product
    actor: student
    entities:
      - { entity: planner, effect: reads, facts: [Matriculation year, Graduation year, iBLOCs] }
    contexts: { web: { place: "web::public::planner" } }
  - text: "The Product shows each planned course with its code, title and units, the units of each semester and year, and the total"
    kind: product
    actor: student
    entities:
      - { entity: planned-course, effect: reads, facts: [Course, Placeholder, Year, Semester, Position] }
      - { entity: course, effect: reads, facts: [Code, Title, Units] }
      - { entity: planner, effect: reads, facts: [Custom course details] }
    contexts: { web: { place: "web::public::planner" } }
---

# See the plan

## Trigger

The student opens the Planner.

## Outcome

The student sees their whole plan with units and warnings.

## Edge cases

- A placeholder counts 4 units.
- Exam dates show only for the current academic year.
