---
name: playwright
description: Use Playwright to inspect and exercise browser workflows, reproduce UI issues, and capture evidence; add automated browser tests only when requested or needed by the implementation scope.
---

# Playwright

Verify a real browser workflow with observable steps and evidence of the result.

## Working approach

- Follow applicable project instructions and existing user preferences for tooling, Git workflow, conventions, and approvals.
- Inspect existing browser automation, test configuration, startup commands, and target environment. Prefer the project's installed Playwright tools or an available browser connector that supports the task.
- Check the available tool's documentation before using it. Do not assume a particular CLI, wrapper script, browser, or authenticated session exists; explain a missing prerequisite before adding dependencies.

## Exercise the workflow

- Establish the target URL, expected behavior, and relevant viewport or browser. Prefer a local or explicitly authorized test environment.
- Inspect the current page before interacting. Use accessible roles, labels, or established test identifiers; refresh snapshots after navigation or significant UI changes rather than reusing stale element references.
- Wait for observable application state instead of arbitrary delays. Check relevant success, empty, loading, and failure behavior in proportion to the request.
- Do not submit purchases, send messages, delete real records, or mutate external data solely because a browser session is available. Use isolated fixtures and existing authorization for side effects.
- Capture screenshots, console errors, network evidence, or traces when they help explain the result. Avoid saving credentials or private page data in artifacts.

## Report and retain useful evidence

- Distinguish a UI defect from a startup, authentication, network, or automation failure. Report the failed step and supporting evidence without claiming an unobserved root cause.
- For requested test files, follow the existing test framework and keep fixtures isolated and assertions focused on user-visible outcomes.
- Store useful artifacts in the project's established output location and identify their paths. Report the environment, steps exercised, observed result, and unverified paths.
