---
name: feature
description: Add, modify, or remove functionality while identifying side effects, preserving behavior outside the intended change, and verifying affected workflows.
---

# Feature

Add, modify, or remove functionality as requested, with particular attention to unintended effects on existing functionality.

## Working approach

- Respond in the user's language unless they request another language.
- Follow applicable project instructions, including AGENTS.md or CLAUDE.md. Leave Git workflow, tooling, coding conventions, and approval requirements to those instructions and existing user preferences; this skill does not override them.
- Start from a short request. Inspect the project before asking questions, infer the affected domains, and use established patterns. Ask only when an unresolved choice materially changes behavior, compatibility, data, or operational impact; offer a concise recommendation.

## Understand the impact before editing

- Determine whether the request adds, modifies, or removes functionality, or combines these operations. Establish the intended behavior change and which existing behavior must remain intact.
- For additions, check interactions with existing workflows. For modifications, distinguish intentional behavior changes from regressions. For removals, trace remaining callers, entry points, configuration, tests, and external consumers; remove only dependencies made obsolete by the requested change.
- Treat feature removal separately from permanent deletion of stored data or destructive migrations. Do not infer authorization for those operations from a feature-removal request; clarify the scope when needed and follow applicable approval requirements.
- Trace relevant callers, consumers, shared code, and data flow beyond the files to be edited. Inspect existing tests and contracts rather than judging impact from file proximity alone.
- Identify concrete risks supported by the code: for example, shared-component behavior, API consumers, persisted data, permissions, caching, background jobs, or performance. Investigate only those relevant to this change.
- Briefly state the meaningful impact areas and how they will be checked. If the feature requires a breaking change or a consequential tradeoff outside the request, resolve it with the user before proceeding with dependent work.

## Implement and verify

- Make the smallest coherent change that satisfies the requested outcome. Preserve contracts and behavior outside the intended change, and avoid unrelated refactoring or dependency changes.
- Validate the intended behavior and existing workflows exposed to the identified risks. For removals, verify that removed entry points are unavailable as intended and retained workflows still function; update obsolete tests to reflect the requested behavior rather than dropping regression coverage. Add or update focused regression tests where practical; include relevant failure paths and integration boundaries.
- Run the project's relevant checks, then review the diff for unintended changes and missed callers. If shared code changes, check its existing consumers as well as the requested behavior.
- Report what changed, which side effects were considered, the checks actually performed and their results, and remaining risks or unverified areas. Do not claim that side effects are impossible or that untested behavior is verified.
