# Testing & Validation Rules

## Principles

- Use a narrow-first strategy: start with the smallest relevant checks, then expand only when shared surfaces are touched.
- Keep validation proportional to risk, but never skip core verification for changed behavior.
- Prefer deterministic checks over manual confirmation when both are available.

## Required Behavior

- Add or update tests when behavior changes.
- For bug fixes, add regression coverage when practical; if not practical, explain why.
- Start with focused checks for touched files, packages, or features.
- Broaden to integration, end-to-end, or full-suite checks when changes impact shared modules, common utilities, or public interfaces.
- If a required check cannot run, document the blocker and perform the best available alternative checks.

## Reporting

- List exact validation commands executed.
- Report outcomes for each command (`pass`, `fail`, or `not run`).
- If any check is skipped, include the explicit reason it was skipped and the risk introduced by skipping it.
- When failures remain unresolved, summarize impact and the next follow-up action.
