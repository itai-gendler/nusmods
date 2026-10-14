---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student opens Today"
    kind: actor
    actor: student
    entities: []
    contexts: { web: { place: "web::public::today" } }
  - text: "The Product works out the semester and teaching week of each of the next seven days in Singapore time"
    kind: product
    actor: student
    entities:
      - { entity: site-configuration, effect: reads, facts: [Holidays] }
    contexts: { web: { place: "web::public::today" } }
  - text: "The Product shows, day by day, the lessons of shown timetable courses that run that week, today's past lessons left out, with the weather forecast"
    kind: product
    actor: student
    entities:
      - { entity: timetable-course, effect: reads, facts: [Course, Lessons chosen, Color] }
      - { entity: course, effect: reads, facts: [Lessons] }
    contexts: { web: { place: "web::public::today" } }
  - text: "The Student opens a lesson"
    kind: actor
    actor: student
    entities: []
    contexts: { web: { place: "web::public::today" } }
  - text: "The Product shows where its venue is on the map"
    kind: product
    actor: student
    entities:
      - { entity: venue, effect: reads, facts: [Name, Location] }
    contexts: { web: { place: "web::public::today" } }
---

# See the coming week

## Trigger

The student opens Today.

## Outcome

The student sees each day's lessons in time order, today's from the current time, with the time left before the next one.

## Edge cases

- Lessons of courses in TA mode show; hidden courses do not.
- In the week before Semester 2 starts, the Semester 2 timetable is used.
