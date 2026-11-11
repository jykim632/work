---
name: gh-fix-ci
description: Investigate and fix failing GitHub Actions checks on a pull request by tracing logs to a specific commit and verifying a scoped correction.
---

# GitHub CI Fix

Diagnose a failing GitHub Actions check and correct its cause within the requested scope.

## Working approach

- Follow applicable project instructions and existing user preferences for Git workflow, tooling, conventions, and approvals.
- Use a suitable connected GitHub tool or authenticated `gh` CLI. Verify the repository, PR, head commit, and failed check before drawing conclusions.
- An investigation-only request does not authorize fixes. A request to fix authorizes scoped local corrections; publishing commits or rerunning workflows requires the corresponding authorization.

## Diagnose the failed check

- Read check status, run metadata, and relevant job logs. Distinguish the current head from an older run and a failed run from one still in progress or canceled.
- Identify the first actionable failure and separate it from downstream errors. Compare the changed code with workflow configuration, runtime versions, and dependency installation when relevant.
- Distinguish a code defect, test defect, environment issue, permission failure, and transient service problem using evidence. Do not label an unexplained failure as flaky.
- If logs are unavailable or checks belong to an unsupported external provider, report the limit and details link instead of inventing a diagnosis.

## Correct and verify

- Reproduce the failing command locally where practical. Make the smallest correction to its cause and add a meaningful regression check when applicable.
- Do not disable checks, weaken assertions, expose secrets, or broaden permissions to obtain a green result. Change dependency versions or workflow configuration only when the requested repair actually requires it.
- Run focused local checks. A local pass does not establish that remote CI passed; report each separately and tie remote results to their commit.
- Rerun CI only when authorized and the workflow's side effects are understood. Avoid repeated retries without new evidence or a stopping condition.
- Report the failed check and run link, cause and evidence, correction, validation results, and remaining remote checks.
