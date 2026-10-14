---
id: nusmods
summary: The open-source course catalogue, course search and timetable builder for students of the National University of Singapore, with exam schedules, a multi-year course planner, free-room search and the university's Course Planning Exercise.
category: course-planner
tags: [course-planner, timetable, university, open-source, open-data]
authors:
  - name: NUSMods contributors
    url: https://github.com/nusmodifications/nusmods
license: MIT
languages: [en]
limitations:
  - There are no NUSMods accounts; timetables, the planner and settings stay in the browser that made them, and a share link carries a timetable to another device or person.
  - Course, exam, lesson and venue information comes from the university and is never edited in NUSMods; a student who finds an error reports it to the faculty.
  - Students sign in, with their NUS account, only to take part in the Course Planning Exercise, and the preferences they give there are kept by the university.
  - Course reviews are discussions held on Disqus, not kept by NUSMods.
  - The Course Planning Exercise records demand for planning only and checks neither timetable clashes nor requisites.
references:
  - { kind: doc, role: intent, target: README.md, title: README }
  - { kind: doc, role: context, target: ARCHITECTURE.md, title: Architecture }
  - { kind: doc, role: context, target: AGENTS.md, title: Agent notes }
  - { kind: code, role: implementation, target: website/src/config/app-config.json }
---

# NUSMods

NUSMods is the course catalogue, course search and timetable builder for
students of the National University of Singapore. Students look up any course
the university offers, with its description, units, requisites, exams, lesson
timetable and student reviews, and find courses by faculty, level, semester,
exam or attributes. They build a timetable for each semester by adding courses
and choosing their classes, see when their exams fall and whether they clash,
and share, sync or download the result. A planner lays out the courses of a
whole degree across years and semesters and flags unmet prerequisites,
semesters a course is not offered in and exam clashes. The Today page shows the
coming week's lessons, the Venues page each room's timetable and the rooms free
at a given time, and an optimiser proposes a timetable that keeps chosen days
free and lessons within chosen hours. During the university's Course Planning
Exercise, students sign in with their NUS account to say which courses they
intend to take. The same course and venue data is published as a public API.

## Intent

In the project's words, its team is "dedicated to enhancing school life through
technology", helping "over 30,000 students every semester in planning their
timetables and finding the best modules to take". It is run by volunteers, so
it stays "pragmatically simple": everything a student builds is kept in their
own browser, and the data it publishes is open for anyone to build on.
