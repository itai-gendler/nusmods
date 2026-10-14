---
kind: primary
routes:
  web: Web
  api: Public API
steps:
  - text: "The refresh schedule comes round"
    kind: condition
    unattended: true
    entities: []
  - text: "The Product reads the university's departments, catalogue, class schedules and exams for every semester of the academic year"
    kind: product
    entities: []
  - text: "The Product adds courses new to the catalogue and updates the rest"
    kind: product
    entities:
      - { entity: course, as: new, effect: creates, to: Offered, facts: [Code, Other codes, Title, Description, Faculty, Department, Units, Semesters offered, Prerequisite, Prerequisite tree, Corequisite, Preclusion, Exam, Lessons, Workload, Grading basis, Additional information, Academic year] }
      - { entity: course, as: existing, effect: changes, facts: [Title, Description, Units, Semesters offered, Prerequisite, Prerequisite tree, Exam, Lessons, Workload] }
  - text: "The Product works out each venue's weekly lessons and occupancy from the lessons"
    kind: product
    entities:
      - { entity: venue, effect: changes, facts: [Lessons, Occupancy] }
    contexts: { web: { place: "web::public::venue" }, api: { place: public-api } }
---

# Take in new course data

## Trigger

The scheduled refresh runs.

## Outcome

New and changed courses, exams, lessons and venue timetables are published.

## Edge cases

- The university's data takes up to a day to reach NUSMods, so the error report form asks students to wait 24 hours before reporting.
