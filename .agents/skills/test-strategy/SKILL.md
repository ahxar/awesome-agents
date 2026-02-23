---
name: test-strategy
description: Plan and refine test strategy for code changes, including test planning, regression tests, acceptance criteria, flaky tests, and risk-based test scope selection.
---

# Test Strategy

Use this skill when a task requires deciding what to test, how deeply to test, and how to report validation coverage.

## Workflow

1. Map the change surface

- Identify touched components, data paths, and public interfaces.
- Mark shared modules and high-impact paths as higher risk.

2. Prioritize failure modes

- List likely regressions and user-visible breakpoints.
- Rank by severity and probability to guide test depth.

3. Define narrow checks first

- Choose the smallest deterministic tests that can quickly validate the change.
- Prefer targeted unit or package-level checks before broader suites.

4. Define expansion criteria

- Expand to integration, end-to-end, or full-suite checks when shared surfaces are affected.
- Expand when narrow checks fail to cover key failure modes.

5. Report verification clearly

- List exact commands and outcomes.
- Call out skipped checks with reasons and residual risk.
- Recommend follow-up checks when immediate coverage is partial.

## Reference

Use `references/check-matrix.md` for a language-agnostic test selection matrix and heuristics by change type.
