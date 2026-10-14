---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student chooses Report errors on a course page"
    kind: actor
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::course-page" } }
  - text: "The Product asks the student to wait up to 24 hours for updates before reporting, picks the faculty contact for the course and fills in the details remembered from the last report"
    kind: product
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [Code, Department, Faculty] }
      - { entity: student, effect: reads, facts: [Contact details] }
    contexts: { web: { place: "web::public::course-page" } }
  - text: "The Student enters their name, email, matriculation number and message, and sends it"
    kind: actor
    actor: student
    entities: []
    contexts: { web: { place: "web::public::course-page" } }
  - text: "The Product remembers the student's name, email and matriculation number and emails the report to the faculty contact"
    kind: product
    actor: student
    entities:
      - { entity: student, effect: changes, facts: [Contact details] }
      - { entity: course, effect: reads, facts: [Code] }
    contexts: { web: { place: "web::public::course-page" } }
---

# Send a report

## Trigger

The student spots an error in a course's information.

## Outcome

The faculty contact for the course is emailed the report; the student's details are remembered for next time.

## Edge cases

- Bugs in NUSMods itself go to bugs@nusmods.com instead.
- For two weeks either side of CourseReg Round 1 the button is made prominent with a link to the FAQ.
