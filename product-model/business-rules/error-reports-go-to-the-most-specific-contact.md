---
appliesTo:
  - { type: capability, id: report-course-error }
  - { type: entity, id: course, facts: [Code, Department, Faculty] }
references:
  - { kind: code, role: implementation, target: website/src/views/modules/ReportError.tsx }
  - { kind: code, role: implementation, target: website/src/data/facultyEmail.json }
---

# Course error reports go to the most specific faculty contact

A report is sent to the contact listed for the course code, else for its code prefix, else its department, else its faculty, separately for undergraduate and graduate (level 5000 and above) courses.
