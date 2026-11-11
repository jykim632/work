---
name: pr
description: Prepare a pull request title and description from an actual diff and verified context; create or update the remote pull request only when requested.
---

# PR

Turn a scoped change into a reviewable pull request description grounded in the actual diff.

## Working approach

- Follow applicable project instructions and existing user preferences for Git workflow, tooling, conventions, and approvals.
- Inspect Git status, the intended base branch, commits, and the full relevant diff. Identify uncommitted changes and distinguish them from what a remote PR would contain.
- Read repository PR templates and linked issues when available. Infer intent from evidence and ask only when an unresolved choice materially changes the PR's scope or destination.

## Prepare the review

- Lead with the concrete problem and resulting behavior. Include a short before/after example when it helps a reviewer understand the change.
- Describe the final implementation, relevant compatibility or operational impact, and meaningful limits. Omit abandoned approaches and conversational history unless they explain a necessary tradeoff.
- State only checks actually run and their results. Identify checks not run; do not turn a proposed test into a validation claim.
- Keep the title and body proportional to the change and follow the repository template. Use issue-closing keywords only when the change actually resolves the issue and closure is intended.

## Publish when requested

- Writing a description does not authorize committing, pushing, or creating a remote PR. Use existing explicit authorization for those actions without requesting it again.
- Before a requested remote operation, verify the repository, head branch, base branch, and existing PR to avoid duplicates or publishing unrelated changes.
- Prefer structured body arguments. With `gh`, write multiline text to a temporary file and use `--body-file` to preserve formatting and avoid shell interpolation.
- Report the prepared title and body, or the resulting PR link after a successful requested publication. Identify any local work not represented in the PR.
