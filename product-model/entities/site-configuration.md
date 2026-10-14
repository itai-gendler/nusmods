---
singleton: true
references:
  - { kind: code, role: implementation, target: website/src/config/app-config.json }
  - { kind: code, role: implementation, target: website/src/config/index.ts }
  - { kind: code, role: implementation, target: website/src/featureFlags.ts }
  - { kind: code, role: implementation, target: website/src/views/mpe/constants.ts }
  - { kind: code, role: implementation, target: website/src/data/modreg-schedule.json }
  - { kind: code, role: implementation, target: website/src/data/holidays.json }
---

# Site configuration

The term settings the NUSMods team sets for each release: which academic year and semester it shows and which university exercises are open.

## Information kept

- **Academic year** — the academic year whose courses and timetables NUSMods shows
- **Current semester** — the semester NUSMods opens on
- **Exam dates available** — the semesters whose exam dates the university has published
- **CPEx open** — whether the Course Planning Exercise is taking responses
- **CPEx round** — the academic year and semester the Course Planning Exercise is for, and its undergraduate and graduate dates
- **CourseReg schedule** — the CourseReg rounds for undergraduates and graduates, with their start and end times
- **Holidays** — the public holidays on which no lessons are held
