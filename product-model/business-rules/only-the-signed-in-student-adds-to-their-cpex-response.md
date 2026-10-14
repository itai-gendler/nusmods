---
appliesTo:
  - { type: entity, id: cpex-course, effect: creates }
permits:
  - { related: [{ verb: lists, entity: cpex-submission }, { verb: owns, entity: student }], when: [{ entity: site-configuration, fact: CPEx open, is: "Yes" }] }
references:
  - { kind: code, role: implementation, target: website/api/nus/mpe/submissions.ts }
  - { kind: code, role: implementation, target: website/src/serverless/nus-auth.ts#verifyLogin }
  - { kind: code, role: implementation, target: website/src/serverless/mpe.ts#featureFlagEnablerMiddleware }
---

# Only the signed-in student adds courses to their CPEx response, while CPEx is open

A response is reached only through its own student's NUS sign-in, and only while the exercise is open.
