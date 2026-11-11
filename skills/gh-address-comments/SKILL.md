---
name: gh-address-comments
description: Evaluate and address review comments on a GitHub pull request with scoped fixes, validation, and evidence-backed dispositions for each requested thread.
---

# GitHub Review Comments

Turn requested PR review feedback into justified corrections and a clear record of what was addressed.

## Working approach

- Follow applicable project instructions and existing user preferences for Git workflow, tooling, conventions, and approvals.
- Use a suitable connected GitHub tool or authenticated `gh` CLI. Verify the repository, PR, current head, and requested review threads.
- Read the full relevant comments, surrounding diff, current implementation, callers, and tests. Account for pagination, replies, and outdated line references before deciding a thread remains actionable.

## Evaluate and implement

- Distinguish actionable defects or requirements from questions, preferences, duplicates, and feedback already satisfied by newer changes.
- Check the reviewer's claim against code and intended behavior. Do not blindly implement feedback that introduces a regression or contradicts the accepted contract.
- If the user requests all actionable feedback, proceed with supported corrections without asking them to select each thread. Ask only when conflicting feedback or an unresolved product decision materially affects the result.
- Implement the smallest coherent fixes for the requested comments, preserving unrelated changes. Run focused checks and inspect affected consumers where shared behavior changes.

## Report dispositions

- For each requested thread, state whether it was addressed, already satisfied, not applicable with evidence, or left unresolved with a reason. Reference the relevant file or test.
- Draft concise replies when useful, explaining the correction and validation rather than claiming success without evidence.
- Posting replies, resolving remote threads, committing, and pushing require the corresponding explicit authorization; a request to make local code corrections alone does not grant it.
- Before an authorized thread resolution, confirm the current code addresses the concern. Do not resolve disagreement or an unverified fix merely to clear the review queue.
- Report local changes and checks separately from any remote replies or resolutions actually completed.
