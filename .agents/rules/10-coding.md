# Coding Rules

- Prefer simple, explicit code over clever abstractions.
- Keep functions small and purpose-specific.
- Reuse existing utilities before adding new dependencies.
- Add comments only where intent is not obvious from code.
- Update nearby documentation when behavior changes.

## Quality checks

- Run the narrowest relevant tests first.
- Expand to broader checks when core changes touch shared paths.
- If checks cannot run, report what was skipped and why.
