---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student opens Courses and types a search"
    kind: actor
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::course-finder" } }
  - text: "The Product shows how many courses match and lists them ten a page with code, title, units, department, faculty, description, requisites and semesters with exam dates, the matching words highlighted"
    kind: product
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [Code, Title, Description, Faculty, Department, Units, Semesters offered, Exam, Prerequisite, Preclusion] }
    contexts: { web: { place: "web::public::course-finder" } }
---

# Search the catalogue

## Trigger

The student looks for courses on a subject.

## Outcome

The student sees the matching courses with how many there are.
