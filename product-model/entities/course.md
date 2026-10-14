---
domain: courses
relations:
  - { entity: timetable-course, verb: is added as, cardinality: one-to-many }
references:
  - { kind: code, role: implementation, target: website/src/types/modules.ts }
  - { kind: code, role: implementation, target: scrapers/nus-v2/src/tasks/DataPipeline.ts }
---

# Course

A course in the university's catalogue for the academic year, with its lessons and exams in each semester it is offered. NUSMods shows past years' catalogues too, as archives.

## Information kept

- **Code** — the course code, such as CS1010S
- **Other codes** — codes the same course is also known by
- **Title** — the course title
- **Description** — what the course covers
- **Faculty** — the faculty that hosts it
- **Department** — the department that hosts it
- **Units** — how many units the course is worth
- **Semesters offered** — Semester 1, Semester 2, Special Term I and Special Term II, as offered
- **Prerequisite** — the prerequisite as the university words it
- **Prerequisite tree** — the prerequisites as a tree of courses, and the courses this one is a prerequisite for
- **Corequisite** — courses to take alongside it
- **Preclusion** — courses that preclude it
- **Exam** — for each semester, the exam date, start time and duration, or none
- **Lessons** — for each semester, the classes of each lesson type, each with its class number, day, time, weeks and venue
- **Workload** — the weekly hours of lectures, tutorials, labs, projects and preparation
- **Grading basis** — how the course is graded
- **Additional information** — attributes such as whether it can be taken as an unrestricted elective, with any further note
- **Academic year** — the academic year the information belongs to

## States

### Offered

Offered in at least one semester of the academic year.

### Not offered

Listed in the catalogue but offered in no semester this academic year.
