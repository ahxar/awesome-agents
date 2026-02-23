---
name: change-readiness
description: Prepare changes for pre-merge hardening and release readiness, including rollout and rollback notes plus final QA pass expectations.
---

# Change Readiness

Use this skill for final hardening before merge or release to ensure changes are understandable, verifiable, and recoverable.

## Workflow

1. Perform a diff audit

- Confirm the diff is focused and free of accidental churn.
- Separate behavior changes from refactors and formatting-only edits.

2. Run a compatibility scan

- Check public interfaces, expected outputs, and integration contracts for breaking impact.
- Flag migration or coordination requirements for downstream users.

3. Check documentation sync

- Verify nearby docs/examples/comments reflect behavior and interface changes.
- Mark stale docs and define required updates.

4. Build verification summary

- Collect commands run, outcomes, and skipped checks with reasons.
- Record remaining confidence gaps and recommended follow-up validation.

5. Produce release risk summary

- Summarize what changed, why it changed, and user-visible effects.
- Provide rollout notes and rollback/recovery guidance for risky changes.
- Highlight unresolved issues that must be tracked post-merge.

## Reference

Use `references/release-checklist.md` for a standard release-readiness checklist template.
