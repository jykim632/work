---
name: diagnosis
description: Diagnose user-reported problems in code, UI, documentation, or configuration; establish scope, reproduce symptoms where practical, and recommend solutions without changing project source, configuration, or tests.
---

# Diagnosis

Determine whether a reported issue is a defect, investigate its cause and impact, and recommend a solution.

Follow applicable project instructions and existing user preferences for language, tooling, Git workflow, conventions, and approvals.

## Establish scope

- Identify the investigation target from the user's request, prior conversation, supplied paths, logs, or other evidence.
- If the target cannot be identified or competing interpretations would lead to different investigations, ask the user to clarify the scope before investigating. An unknown cause alone does not require clarification.
- Briefly state the starting scope. Inspect relevant implementation, documentation, callers, and existing tests, following directly related calls and data flow as needed.
- If evidence requires expanding into a separate feature or system beyond the established scope, explain why and confirm the expansion unless already authorized.

## Determine expected behavior and verification

- Establish expected behavior from the user's report, requirements, existing contracts, design references, or authoritative sources. Do not assume that current code, documentation, or tests are correct.
- Do not classify a visual preference as a defect without an applicable expectation.
- Inspect relevant code, existing test coverage, and the actual execution environment before selecting a verification approach.

For UI issues, use the evidence needed to select the approach:

| Evidence needed | Preferred approach |
| --- | --- |
| Inputs, state changes, event handling, or resulting DOM content can establish the finding | Existing Testing Library tests |
| Actual layout, clipping, overlap, scrolling, or browser-dependent interaction must be observed | Playwright |
| Browser behavior and component behavior each require separate evidence | Both, with a distinct purpose for each |

- Account for the actual environment: Testing Library commonly runs with jsdom, which does not perform layout, but it can also run in a browser.
- Apply the selection criteria after inspecting code and existing tests. If that inspection still cannot distinguish browser behavior from component logic for the reported symptom, observe the symptom in the browser first.
- Add component or browser verification only when it answers a remaining question. Do not use both tools by default or repeat equivalent checks without a concrete reason.
- Prefer existing project tooling. If a selected tool or prerequisite is unavailable, explain the limitation and use an available alternative only if it can provide the required evidence.
- Before execution, briefly state the target, selected approach, reason, and conditions that would justify additional verification.

## Investigate and reproduce

- Reproduce the reported conditions and actions where practical.
- Before running an existing test, check whether it exercises the reported conditions. A passing test for a different scenario is supporting evidence, not reproduction.
- If the reported conditions cannot be exercised within the diagnosis boundaries, report the symptom as not reproduced and continue with available inspection evidence.
- For UI reproduction, use the relevant page, viewport, and application state. Inspect the rendered result when the issue concerns appearance or browser interaction.
- A passing component test does not establish that the rendered browser UI is correct.
- Separate failures caused by startup, authentication, network, or tooling from the reported application defect.
- Test plausible causes against available evidence. Distinguish observed behavior, conclusions supported by code inspection, and unverified hypotheses.
- For documentation or configuration issues, compare claims, examples, and settings with intended behavior and authoritative sources. Investigate conflicting evidence and disclose remaining uncertainty.
- Identify affected workflows and likely side effects of proposed fixes within the established scope.
- End the investigation when the evidence supports an answer to the scoped question and an actionable recommendation. If further progress depends on unavailable evidence or work outside the permitted scope, report that limit and the next useful check. Do not continue merely to exhaust every possible hypothesis.

## Diagnosis boundaries

- Do not add or modify project source, configuration, dependencies, test files, or reference snapshots. Do not run automatic fixes or snapshot updates.
- Use checks that preserve real data and external state.
- Generated logs, reports, caches, screenshots, and traces are allowed in established disposable output locations or temporary directories. Treat them as investigation artifacts, not project changes.
- Capture artifacts only when useful as evidence, follow project conventions, and avoid collecting secrets or private data.
- Do not automatically install missing dependencies or change the project setup to enable verification.

## Report findings

- State whether a defect was confirmed and whether the symptom was reproduced.
- Explain the cause when established, supporting evidence, affected workflows, and prioritized recommendations.
- Report the environment and checks actually used, material limitations, and unverified paths.
- If unresolved, identify the missing evidence and next useful check. Do not present code inspection alone as successful browser reproduction.

An explicit request to implement a fix starts a separate fixing phase. Reuse the findings already gathered without requiring the user to repeat the context or invoke another command.
