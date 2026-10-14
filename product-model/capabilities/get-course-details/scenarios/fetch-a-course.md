---
kind: primary
routes:
  api: Public API
steps:
  - text: "The Developer requests a course by code for an academic year"
    kind: actor
    actor: developer
    entities:
      - { entity: course, effect: reads, facts: [] }
    contexts: { api: { place: public-api } }
  - text: "The Product returns the course with its details, requisites, prerequisite tree and each semester's lessons and exam"
    kind: product
    actor: developer
    entities:
      - { entity: course, effect: reads, facts: [Code, Title, Description, Faculty, Department, Units, Prerequisite, Prerequisite tree, Corequisite, Preclusion, Exam, Lessons, Workload] }
    contexts: { api: { place: public-api } }
---

# Fetch a course

## Trigger

A developer needs one course.

## Outcome

The developer has the course's full details.
