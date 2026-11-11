# Repository instructions

This repository maintains reusable Codex workflows under `skills/`.

## Skill conventions

- Follow the existing `skills/feature/SKILL.md` format. Write skill instructions in English and respond to the user in Korean by default.
- Store each skill in `skills/<name>/SKILL.md`. Use a lowercase, hyphenated name matching the folder and YAML frontmatter containing `name` and `description`.
- Explain the skill's scope in its description. Keep the body focused on its outcome, relevant decisions, verification, and reporting.
- Defer Git workflow, permissions, tooling, and project conventions to the target project's instructions and existing user authorization. Do not duplicate a global policy in every skill.
- Keep ordinary skills self-contained. Add scripts, references, assets, or UI metadata only when the workflow needs them; verify referenced resources exist.
- A skill must not imply permission to publish, send messages, deploy, or modify production data merely because it was selected.
- Preserve unrelated changes and existing skills. Use a dedicated Git worktree for changes; do not commit or push unless requested.

## Verification

- Run the available `skill-creator` frontmatter validator for each added or changed skill, and review scope, tool assumptions, and authorization boundaries manually.
- Keep the root README's skill index consistent with the files included in the change. Do not add per-skill README files for simple instruction-only skills.
- Report checks actually performed and distinguish static validation from exercising a workflow against a real service.
