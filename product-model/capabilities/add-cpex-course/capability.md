---
domain: cpex
availability:
  - { place: web::signed-in }
references:
  - { kind: code, role: implementation, target: website/src/views/mpe/form/ModuleForm.tsx }
  - { kind: code, role: implementation, target: website/src/views/mpe/form/ModulesSelectContainer.tsx }
  - { kind: code, role: implementation, target: website/src/views/mpe/UpdateSubmissionQueue.ts }
  - { kind: code, role: implementation, target: website/src/serverless/mpe.ts#createSubmission }
---

# Add a CPEx course

Add a course the student intends to take to their CPEx response.
