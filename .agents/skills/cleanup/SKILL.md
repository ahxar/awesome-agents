---
name: cleanup
description: "Run a post-implementation cleanup pass for completed features in any programming language. Use when a feature is already built and the user asks to polish, harden, simplify, or prepare code for review/merge. Apply cross-language best practices: remove temporary code, improve readability and consistency, strengthen edge-case handling, update tests/docs, and run the repository's relevant quality checks."
---

# Cleanup

Execute this skill after implementing a feature to raise quality without changing intended behavior.

## Workflow

1. Define scope

- Identify files touched by the feature.
- Keep edits focused on those files unless a direct dependency requires a small follow-up.
- Preserve current behavior and contracts unless the user asked for behavior changes.

2. Run code hygiene cleanup

- Remove dead code, unused imports, and commented-out blocks.
- Remove temporary debug logs, tracing prints, and throwaway flags.
- Resolve obvious TODO/FIXME items created during implementation.
- Simplify unnecessarily complex logic while preserving behavior.

3. Enforce consistency

- Align naming, error style, and file structure with existing project patterns.
- Normalize formatting and style using project-standard tools.
- Keep APIs consistent across adjacent modules changed by the feature.

4. Improve robustness

- Handle edge cases and invalid input paths introduced by the feature.
- Ensure errors are actionable and not silently swallowed.
- Preserve idempotency and retry safety for mutating operations where relevant.

5. Update verification

- Add or update focused tests for changed behavior.
- Run the narrowest relevant checks first, then broader checks if needed.
- Fix any lint/type/format/test issues introduced by the feature work.

6. Update documentation

- Update nearby docs, examples, or comments when behavior or interfaces changed.
- Remove stale documentation that no longer matches implementation.

7. Finalize

- Re-check diff for accidental churn.
- Summarize cleanup actions and validation commands executed.

## Guardrails

- Do not introduce intentional behavior changes during cleanup.
- Do not start broad refactors unrelated to the completed feature.
- Do not touch unrelated files to satisfy stylistic preferences.
- If a required tool cannot run, state it and continue with the best available checks.

## Language Coverage

Use this skill for any language. Select repository-native tools first (existing scripts, make targets, CI commands), then use common ecosystem defaults from `references/language-checks.md` when needed.
