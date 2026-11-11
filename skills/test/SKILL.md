---
name: test
description: Add or strengthen automated tests for existing behavior, including regression coverage and failure paths, without changing product behavior to satisfy tests.
---

# Test

Improve confidence in an existing workflow through focused tests that exercise observable behavior.

## Working approach

- Follow applicable project instructions and existing user preferences for tooling, Git workflow, conventions, and approvals.
- Inspect the relevant implementation, public callers, fixtures, and nearby tests. Reuse the existing test framework and commands.
- Establish expected behavior from requirements and contracts. Do not assume the implementation or an existing assertion is correct.

## Identify useful coverage

- Prioritize missing coverage supported by a concrete risk or reported defect. Cover the success path, meaningful boundaries, and expected failures where relevant.
- Choose the narrowest test level that can observe the behavior. Use integration tests when the risk lies across a real boundary rather than mocking that boundary away.
- Keep tests deterministic and isolated from production data, external accounts, and wall-clock timing. Mock external systems at established boundaries without reproducing the implementation inside the test.

## Implement and verify

- Add clear assertions on outcomes, errors, or side effects. Avoid tests that only assert internal call order or repeat implementation logic without a behavioral reason.
- For a regression, demonstrate that the test exposes the reported defect when practical. Distinguish an expected regression failure from a broken test setup.
- Do not weaken assertions or alter product behavior merely to get a passing result. If testing reveals a defect, report it; fix it only when the requested scope includes implementation changes.
- Run the focused tests and relevant formatter or type checks. Broaden verification when shared fixtures or helpers change.
- Report coverage added, commands and results, any exposed defects, and remaining unverified behavior.
