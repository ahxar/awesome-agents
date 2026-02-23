# Security & Dependency Rules

## Secrets and Sensitive Data

- Never add secrets, tokens, credentials, private keys, or production-sensitive configuration to tracked files.
- Treat logs, fixtures, and examples as production-visible unless explicitly proven otherwise.
- When touching authentication, authorization, or sensitive-data paths, call out security impact before applying risky changes.

## Dependency Hygiene

- Prefer pinned or appropriately constrained dependency versions for the language ecosystem in use.
- Reuse existing project dependencies before introducing new ones.
- Justify any new dependency by purpose, maintenance quality, and security posture.
- If dependency or vulnerability scans are available, run the narrowest relevant scan first.

## Risk Escalation

- Explicitly assess and report risks when changes affect authentication or authorization rules.
- Explicitly assess and report risks when changes affect permissions and access control boundaries.
- Explicitly assess and report risks when changes affect input validation and injection surfaces.
- Explicitly assess and report risks when changes affect data exposure, logging, or storage of sensitive fields.
- Document unresolved vulnerabilities, blocked scans, or deferred remediations with rationale and expected follow-up.
