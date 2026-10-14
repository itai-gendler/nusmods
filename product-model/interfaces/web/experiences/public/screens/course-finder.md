---
entities:
  - { entity: course, shows: [Code, Title, Description, Faculty, Department, Units, Semesters offered, Exam, Prerequisite, Preclusion] }
entryPoints:
  - web: /courses
references:
  - { kind: code, role: implementation, target: website/src/views/modules/ModuleFinderContainer/ModuleFinderContainer.tsx }
---

# Course finder

Search and filter the catalogue.
