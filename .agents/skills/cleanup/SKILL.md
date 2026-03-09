---
name: cleanup
description: "Comprehensive post-implementation and post-refactor cleanup pass for completed work in any programming language. Trigger this skill when requests mention cleanup, polish, harden, deduplicate, reduce tech debt, remove unused or dead code, reuse existing functions/types/modules, consolidate duplicate implementations, or prepare changes for review/merge. Execute a behavior-preserving, less-is-more cleanup that prioritizes deletion and simplification before adding abstractions, then run focused quality checks."
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

3. Run a less-is-more pass

- Reuse existing functions, types, and modules before introducing new ones.
- Consolidate repeated implementations into shared code only when behavior and contracts remain unchanged.
- Remove unused functions, types, methods, imports, and dead branches.
- Prefer deletion and simplification over new abstractions unless duplication cannot be safely removed.
- If cleanup increases total code size, provide an explicit justification tied to maintainability or risk reduction.

4. Enforce consistency

- Align naming, error style, and file structure with existing project patterns.
- Normalize formatting and style using project-standard tools.
- Keep APIs consistent across adjacent modules changed by the feature.

5. Improve robustness

- Handle edge cases and invalid input paths introduced by the feature.
- Ensure errors are actionable and not silently swallowed.
- Preserve idempotency and retry safety for mutating operations where relevant.

6. Update verification

- Add or update focused tests for changed behavior.
- Run the narrowest relevant checks first, then broader checks if needed.
- Fix any lint/type/format/test issues introduced by the feature work.

7. Update documentation

- Update nearby docs, examples, or comments when behavior or interfaces changed.
- Remove stale documentation that no longer matches implementation.

8. Finalize

- Re-check diff for accidental churn.
- Summarize cleanup actions and validation commands executed.

## Guardrails

- Do not introduce intentional behavior changes during cleanup.
- Do not start broad refactors unrelated to the completed feature.
- Do not touch unrelated files to satisfy stylistic preferences.
- Treat this as a behavior-preserving pass unless the user explicitly asks for behavior changes.
- If a required tool cannot run, state it and continue with the best available checks.

## Language Coverage

Use this skill for any language. Select repository-native tools first (existing scripts, make targets, CI commands), then use common ecosystem defaults from `references/language-checks.md` when needed.

## Evidence

- [Google Cloud DORA, 2025: The Impact of Gen AI in Software Development](https://services.google.com/fh/files/misc/dora_state_of_devops_gen_ai_2025.pdf) reports speed and flow improvements, while showing reliability and delivery outcomes still depend on disciplined engineering practices.
- [AI-Assisted Programming Decreases Code Quality Through Reduced Human Oversight (arXiv, 2025)](https://arxiv.org/abs/2504.16306) finds quality regressions when review rigor drops, reinforcing explicit cleanup and simplification gates.
- [The Impact of AI Suggestions on Software Development Security (arXiv, 2025)](https://arxiv.org/abs/2505.23023) identifies security regressions from accepted AI suggestions, supporting reuse-first and deletion-first review habits.
- [GitClear, Coding on Copilot 2024](https://www.gitclear.com/coding_on_copilot_data_shows_ais_downward_pressure_on_code_quality) reports increased code churn and duplication trends in AI-heavy workflows, motivating deduplication and unused-code removal after refactors.
