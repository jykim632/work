---
name: fix
description: Correct defects in code, documentation, or configuration by establishing expected behavior, identifying the cause, and verifying the correction and affected workflows.
---

# Fix

Correct a reported defect while preserving behavior outside the intended correction. A symptom supplied with this command requests investigation, correction, and verification. If the user explicitly asks only for inspection, investigate and report without editing.

## Working approach

- Respond in the user's language unless they request another language.
- Follow applicable project instructions and existing user preferences for tooling, Git workflow, conventions, and approvals.
- Start from a short request. Inspect relevant implementation, documentation, callers, and tests before asking questions.
- Establish expected behavior from the user's report, requirements, existing contracts, or authoritative sources. Do not assume that current implementation or tests are correct.
- Ask only when unresolved ambiguity materially changes the correction. Distinguish repairing a defect from introducing a new requirement.

## Diagnose before changing

- Reproduce the problem where practical. Otherwise, gather enough evidence to explain the defect and state what could not be reproduced. Avoid checks that mutate real data or external state without authorization.
- Trace the cause and affected workflows. Separate confirmed findings from hypotheses.
- For documentation defects, check claims, examples, and instructions against intended behavior and authoritative sources. If code and documentation disagree, determine which reflects the intended contract before choosing a correction.
- Check similar cases and shared consumers that may have the same defect or be affected by the fix. Keep investigation proportional to the evidence.

## Fix and verify

- Make the smallest coherent correction that addresses the cause. Avoid unrelated cleanup and changes that merely hide the symptom.
- Preserve behavior outside the intended correction. If a proper fix requires a breaking change, data modification, or broader work, explain the impact and resolve consequential choices with the user within applicable approval requirements.
- Demonstrate the defect before the correction and verify it afterward where practical. Add a regression test or another durable check when it meaningfully prevents recurrence.
- Check relevant failure paths and existing workflows exposed to the change. For documentation, validate corrected claims, links, and runnable examples as applicable.
- Report the cause, correction, side effects considered, checks actually performed and their results, and remaining uncertainty. Do not claim a confirmed root cause or successful verification without supporting evidence.
