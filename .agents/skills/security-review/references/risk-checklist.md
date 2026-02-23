# Security Risk Checklist

## Threat Surface

- Untrusted input reaches command, query, template, file, or network sinks.
- Missing or weak validation for type, range, format, or size.
- Authorization checks absent, bypassable, or inconsistent across paths.

## Secrets and Sensitive Data

- Secrets/tokens present in source, fixtures, logs, or error messages.
- Sensitive fields over-collected, over-shared, or retained too long.
- Missing redaction or masking in telemetry and diagnostics.

## Dependency Risk

- Newly introduced dependencies with unclear maintenance or security posture.
- Major version upgrades without compatibility/risk review.
- Known vulnerabilities without mitigation or tracking note.

## Remediation Patterns

- Validate early and reject invalid input with explicit errors.
- Apply least-privilege authz checks at every privileged boundary.
- Centralize secret access via environment or secret manager patterns.
- Redact sensitive values before logging or exposing errors.
- Pin or constrain dependency versions and document update rationale.

## Finding Format

- Finding:
- Severity:
- Confidence:
- Affected surface:
- Impact:
- Recommended fix:
- Residual risk:
