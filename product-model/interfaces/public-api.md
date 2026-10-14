---
type: api
actors: [developer]
entryPoints:
  - api: https://api.nusmods.com/v2/
references:
  - { kind: doc, role: intent, target: README.md, title: README }
  - { kind: code, role: implementation, target: scrapers/nus-v2/src/services/io/fs.ts }
  - { kind: doc, role: intent, target: scrapers/nus-v2/docs/index.html, title: API documentation }
---

# NUSMods public API

The public, read-only API at api.nusmods.com that publishes the course and
venue data NUSMods itself uses, for each academic year, for anyone to build
on. The project asks that it be used considerately.
