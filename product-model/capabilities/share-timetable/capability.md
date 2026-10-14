---
domain: timetable
availability:
  - { place: web::public }
references:
  - { kind: code, role: implementation, target: website/src/views/timetable/ShareTimetable.tsx }
  - { kind: code, role: implementation, target: website/src/views/routes/paths.ts#timetableShare }
  - { kind: code, role: implementation, target: website/src/utils/timetables/index.ts }
---

# Share a timetable

Get a link to the semester's timetable, to send to friends or to open on another device to sync it, with a QR code and ready-made email, WhatsApp and Telegram messages. The link carries the courses, their chosen classes and which are hidden or in TA mode.
