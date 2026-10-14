---
availability:
  - { place: web::public }
  - { place: public-api }
references:
  - { kind: code, role: implementation, target: scrapers/nus-v2/src/tasks/DataPipeline.ts }
  - { kind: code, role: implementation, target: scrapers/nus-v2/src/tasks/GetSemesterData.ts }
  - { kind: code, role: implementation, target: scrapers/nus-v2/src/tasks/GetSemesterExams.ts }
  - { kind: code, role: implementation, target: scrapers/nus-v2/src/tasks/CollateVenues.ts }
  - { kind: code, role: implementation, target: scrapers/nus-v2/src/tasks/CollateModules.ts }
  - { kind: doc, role: context, target: scrapers/nus-v2/README.md, title: Scraper README }
---

# Refresh course data

Bring the catalogue, exams, lessons and venues up to date from the university's systems, every few hours. The refreshed data is what the website shows and the public API publishes.
