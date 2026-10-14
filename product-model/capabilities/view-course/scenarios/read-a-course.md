---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student opens a course page"
    kind: actor
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::course-page" } }
  - text: "The Product shows the code and any other codes, title, department, faculty, units, semesters offered, description, prerequisite, corequisite, preclusion, additional information, workload and grading basis"
    kind: product
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [Code, Other codes, Title, Department, Faculty, Units, Semesters offered, Description, Prerequisite, Corequisite, Preclusion, Additional information, Workload, Grading basis] }
    contexts: { web: { place: "web::public::course-page" } }
  - text: "The Product shows each semester's exam, the prerequisite tree and the lesson timetable of each semester"
    kind: product
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [Exam, Prerequisite tree, Lessons] }
      - { entity: timetable, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::course-page" } }
  - text: "The Product loads student reviews and discussion from Disqus, with the review guidelines"
    kind: product
    actor: student
    entities:
      - { entity: student, effect: reads, facts: [Load reviews manually] }
    contexts: { web: { place: "web::public::course-page" } }
---

# Read a course

## Trigger

The student opens a course page.

## Outcome

The student sees the course's details, requisites, exams, lessons and reviews.

## Edge cases

- Requisites name other courses as links to their pages.
- With Load reviews manually on, reviews load only when the student asks.
- An old course link under /modules opens the same page.
