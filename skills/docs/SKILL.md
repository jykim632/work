---
name: docs
description: Create or update repository documentation and runnable examples to match intended behavior, configuration, and public contracts.
---

# Docs

Keep repository documentation accurate and useful for its intended readers.

## Working approach

- Follow applicable project instructions and existing user preferences for tooling, Git workflow, conventions, and approvals.
- Locate the relevant README, guides, configuration examples, implementation, tests, and public callers. Follow the existing documentation structure and language.
- Identify the reader's task and intended contract. If documentation and implementation disagree, establish which is correct rather than automatically documenting the current implementation.

## Write and verify

- Update the smallest coherent set of pages affected by the request. Keep shared facts in one maintained location and link to it where appropriate.
- Explain prerequisites, actual commands, expected outcomes, and relevant failure handling at the level the reader needs. Preserve supported compatibility and setup paths.
- Verify external technical claims against authoritative current sources. Do not invent flags, defaults, environment variables, or platform capabilities.
- Use placeholders for credentials and private values. Check examples for unintended effects before executing them; validate syntax or use an isolated environment when execution would modify external state.
- Run available documentation checks and verify changed local links and examples where practical. Update generated documentation through its existing source and generator.
- Report what was corrected, supporting checks, and examples or claims that could not be verified. Report product defects discovered during documentation work without silently expanding into implementation changes.
