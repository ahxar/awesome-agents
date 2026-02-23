---
name: security-review
description: Review changes for security risks involving auth, authorization, secrets, injection, sensitive data handling, and dependency risk.
---

# Security Review

Use this skill for security-focused analysis of code changes, especially when access control, untrusted input, or sensitive data may be impacted.

## Workflow

1. Identify trust boundaries

- Determine where untrusted inputs enter and where privileged operations occur.
- Mark boundaries between client/server, service/service, and role/permission contexts.

2. Enumerate inputs and sinks

- List input vectors (API params, headers, files, env vars, external payloads).
- Map sensitive sinks (DB writes, command execution, templating, logging, serialization).

3. Assess authentication and authorization

- Verify caller identity checks are present where required.
- Verify permission checks enforce least privilege and correct scope.

4. Validate secrets and data handling

- Confirm secrets are not hardcoded or leaked in logs or errors.
- Confirm sensitive fields are minimized, redacted, and protected in transit/storage where relevant.

5. Classify findings and recommend mitigation

- Classify findings by severity and confidence.
- Provide concrete remediation steps and any compensating controls.
- Note residual risk when a mitigation is deferred.

## Reference

Use `references/risk-checklist.md` for a lightweight threat checklist and common remediation patterns.
