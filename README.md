# awesome-agents

Repository for agent operating guidance and shared quality rules.

## Purpose

This repository follows the [AGENTS.md format](https://agents.md/):

- `README.md` is for human contributors.
- `AGENTS.md` is a dedicated instructions file for coding agents.

## AGENTS.md In This Repo

The root `AGENTS.md` points agents to canonical rules in `.agents/rules/`.
These rule files are the source of truth for this repository:

- `.agents/rules/00-general.md`
- `.agents/rules/10-coding.md`
- `.agents/rules/20-testing-validation.md`
- `.agents/rules/30-security-dependencies.md`
- `.agents/rules/40-change-readiness.md`

## Format Notes

Per [agents.md](https://agents.md/):

- `AGENTS.md` is standard Markdown with no required schema.
- Treat `AGENTS.md` as living documentation and keep it current.
- Include practical instructions agents can execute directly.

## Precedence Rules

Per [agents.md](https://agents.md/):

1. The closest `AGENTS.md` to the edited file takes precedence.
2. Explicit user chat instructions override file instructions.

## Suggested AGENTS.md Content

The [agents.md](https://agents.md/) guidance recommends documenting:

- Project overview
- Build and test commands
- Code style guidelines
- Testing instructions
- Security considerations

## Repository Layout

- `README.md`: human-facing project context.
- `AGENTS.md`: agent entry-point instructions.
- `.agents/rules/`: canonical policy and quality requirements.
- `.agents/skills/`: task-specific instructions and workflows.

## Maintenance Notes

- Keep `README.md` concise and human-focused.
- Keep `AGENTS.md` practical and agent-focused (commands, testing, style, and constraints).
- When adding subprojects, add nested `AGENTS.md` files where subproject-specific instructions are needed.
