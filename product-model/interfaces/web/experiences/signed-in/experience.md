---
actors: [student]
access: authenticated
entryPoints:
  - web: /cpex
references:
  - { kind: code, role: implementation, target: website/src/views/mpe/MpeContainer.tsx }
  - { kind: code, role: implementation, target: website/src/serverless/nus-auth.ts }
---

# Signed in with NUS

Where a student who has signed in with their NUS account gives their Course
Planning Exercise response: the courses they intend to take, in order, with
what each counts towards, and the units they intend to take.
