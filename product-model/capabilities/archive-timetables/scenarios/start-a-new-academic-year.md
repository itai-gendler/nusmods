---
kind: primary
routes:
  web: Web
steps:
  - text: "The student's saved timetables belong to an earlier academic year than NUSMods shows"
    kind: condition
    unattended: true
    entities:
      - { entity: timetable, as: last-year, effect: reads, facts: [Academic year] }
      - { entity: site-configuration, effect: reads, facts: [Academic year] }
      - { entity: student, effect: reads, facts: [] }
  - text: "The Product archives the saved timetables"
    kind: product
    entities:
      - { entity: timetable, as: last-year, effect: changes, from: Current, to: Archived, facts: [] }
  - text: "The Product starts an empty timetable for each semester of the new academic year"
    kind: product
    entities:
      - { entity: timetable, as: this-year, effect: creates, to: Current, facts: [Semester, Academic year] }
    contexts: { web: { place: "web::public::timetable" } }
---

# Start a new academic year

## Trigger

The student opens NUSMods after it has moved to a new academic year.

## Outcome

Every semester's timetable is empty; last year's are kept aside and not shown.
