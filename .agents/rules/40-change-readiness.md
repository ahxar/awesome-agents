# Change Readiness Rules

## Change Summary Standard

- For non-trivial work, provide a concise summary of what changed and why.
- Separate behavior changes from refactors, cleanups, and non-functional edits.
- Highlight user-visible or API-visible effects explicitly.

## Compatibility and Rollback

- Call out compatibility impact when interfaces, contracts, or expected outputs change.
- For risky changes, provide rollback or recovery notes that can be executed quickly.
- Record known limitations, deferred work, and operational caveats before handoff.

## Documentation Expectations

- Update nearby documentation, examples, and comments when behavior or interfaces change.
- Remove stale documentation that no longer reflects current behavior.
- If docs are intentionally deferred, state what is missing and the risk of leaving it stale.
