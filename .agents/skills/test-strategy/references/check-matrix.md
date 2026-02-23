# Test Selection Matrix

## Purpose

Use this matrix to choose the smallest reliable checks first, then expand coverage only where risk warrants it.

## Matrix by Change Type

| Change type | Minimum checks | Expand when | Typical expansion |
|---|---|---|---|
| Pure refactor (no behavior change) | Static analysis + targeted existing tests | Shared utility touched or uncertain behavior parity | Package/module suite |
| Bug fix | Repro test + focused regression test | Bug touches shared path or cross-service contract | Integration tests |
| New feature | Acceptance tests for new path + focused unit tests | Shared interfaces, persistence, or orchestration changed | End-to-end smoke + broader suite |
| Dependency update | Lockfile/build verification + targeted affected tests | Major version bump, transitive security risk, runtime uncertainty | Full test suite + compatibility checks |
| Performance optimization | Baseline correctness tests + targeted perf check | Runtime behavior altered or concurrency changed | Integration + stress/regression checks |

## Heuristics

- Prioritize tests that validate critical business flows first.
- Prefer deterministic and fast checks over flaky or slow checks.
- Add one regression test per confirmed bug when practical.
- Expand scope when confidence is low, blast radius is high, or coverage is uncertain.

## Reporting Template

- Commands run:
- Result per command:
- Skipped checks:
- Reason for each skip:
- Residual risk:
- Recommended follow-up:
