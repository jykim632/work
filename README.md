# work
list of AI using work style

## Skills

Reusable workflows live in `skills/<name>/SKILL.md`. Follow [AGENTS.md](AGENTS.md) when adding or updating them.

Each skill's `README.md` is its Korean translation. Keep translations in sync with the English `SKILL.md`, which remains the authoritative instruction source.

| Skill | Purpose | Korean translation |
| --- | --- | --- |
| [brainstorming](skills/brainstorming/SKILL.md) | Explore alternative approaches and refine a direction before implementation. | [한글](skills/brainstorming/README.md) |
| [analysis](skills/analysis/SKILL.md) | Explain behavior and structure, evaluate designs, and assess change impact using evidence. | [한글](skills/analysis/README.md) |
| [diagnosis](skills/diagnosis/SKILL.md) | Diagnose reported problems and recommend solutions without changing source, configuration, or tests. | [한글](skills/diagnosis/README.md) |
| [fix](skills/fix/SKILL.md) | Correct reported defects and verify the correction and affected workflows. | [한글](skills/fix/README.md) |
| [feature](skills/feature/SKILL.md) | Add, modify, or remove functionality while checking affected workflows. | [한글](skills/feature/README.md) |
| [test](skills/test/SKILL.md) | Add focused tests for existing behavior and regressions. | [한글](skills/test/README.md) |
| [pr](skills/pr/SKILL.md) | Prepare a reviewable PR title and description; publish when requested. | [한글](skills/pr/README.md) |
| [docs](skills/docs/SKILL.md) | Align repository documentation and examples with intended behavior. | [한글](skills/docs/README.md) |
| [perf](skills/perf/SKILL.md) | Diagnose and improve runtime performance using measurements. | [한글](skills/perf/README.md) |
| [handoff](skills/handoff/SKILL.md) | Capture verified context and next actions for continuing work. | [한글](skills/handoff/README.md) |
| [playwright](skills/playwright/SKILL.md) | Inspect browser workflows and capture reproducible UI evidence. | [한글](skills/playwright/README.md) |
| [gh-fix-ci](skills/gh-fix-ci/SKILL.md) | Diagnose and repair failing GitHub Actions checks. | [한글](skills/gh-fix-ci/README.md) |
| [gh-address-comments](skills/gh-address-comments/SKILL.md) | Evaluate PR review feedback and implement scoped corrections. | [한글](skills/gh-address-comments/README.md) |

These folders are source files; adding them here does not install them into a user-level skill directory. The browser and GitHub workflows are local adaptations for this repository, not copies of upstream helper scripts.
