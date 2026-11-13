---
name: analysis
description: Explain existing behavior and structure, evaluate specified designs, and assess proposed changes using evidence from code, documentation, and relevant sources without modifying the project.
---

# Analysis

Answer the user's question about how something works, how it is structured, whether a specified approach fits its requirements, or what a proposed change would affect. Do not assume that analysis must find a defect or recommend a change.

## Establish the question and scope

- Follow applicable project instructions and existing user preferences for language, tooling, Git workflow, conventions, and approvals.
- Identify the subject and the question to answer from the request and prior conversation.
- Determine whether the user wants an explanation, structural analysis, evaluation, comparison of specified options, change-impact assessment, or a combination.
- Ask before investigating when the subject or purpose is unclear enough to lead to materially different analyses. Do not require the user to select a category when their intent is already clear.
- Briefly state the question and starting scope. Follow directly relevant dependencies and consumers; confirm expansion into separate features or systems unless already authorized.

## Gather and interpret evidence

- Inspect relevant implementation, documentation, configuration, callers, and existing tests. Treat each as evidence rather than assuming any one source is authoritative.
- For behavior and structure, trace entry points, responsibilities, data flow, state transitions, and dependencies relevant to the question.
- For evaluation or comparison, establish the requirements and criteria before judging suitability. Explain tradeoffs in relation to those criteria rather than personal preference.
- For change-impact analysis, trace affected contracts, consumers, stored data, and workflows. Distinguish direct effects from conditional or speculative effects.
- Use existing checks or browser observation only when they can resolve a concrete uncertainty. Explain the purpose before execution.
- Distinguish facts, inferences, assumptions, and unresolved questions. Investigate conflicting evidence when it affects the conclusion.

## Boundaries and completion

- Do not modify project source, configuration, dependencies, tests, or reference snapshots. Do not install tools or run automatic fixes to enable the analysis.
- Use checks that preserve real data and external state. Keep useful generated evidence in established disposable output locations or temporary directories, without collecting secrets or private data.
- Keep recommendations proportional to the request. An explanation does not automatically require redesign, and an evaluation may conclude that the current approach is appropriate.
- Stop when the scoped question has a sufficiently supported answer. If missing evidence prevents a conclusion, identify the limitation and the next useful check.

## Report the answer

- Lead with the answer to the user's question, then explain the supporting evidence and reasoning.
- Match the output to the purpose: a flow explanation, responsibility and dependency map, criteria-based assessment, comparison, or impact summary.
- Reference relevant code or sources and distinguish observed behavior from conclusions based only on inspection.
- State material assumptions and uncertainties. Include recommendations or next steps when requested or needed to resolve the question.

If the user explicitly requests implementation afterward, continue using the established findings without requiring them to repeat the context or invoke another command.
