---
name: golang-best-practices
description: Apply Go coding, API design, and review best practices distilled from Effective Go, Go Code Review Comments, and Uber's Go Style Guide. Use when writing, reviewing, or refactoring Go packages, services, libraries, tests, concurrency flows, and error handling to keep code idiomatic, clear, and maintainable.
---

# Go Best Practices

Use this skill to implement and review idiomatic Go.

## Workflow

1. Confirm task scope and package boundaries.
2. Run formatter and imports on changed files.
3. Apply rules from `references/rules.md`.
4. Re-run narrow checks first, then broader checks.
5. Summarize which rules drove each meaningful change.

## Baseline Checks

Run what is available in the repository:

- `gofmt -w ./...` or on changed files only.
- `goimports -w` on changed files when available.
- `go test ./...` or the narrowest package scope first.
- `staticcheck ./...` when configured.
- `golangci-lint run` when configured.

## Core Rules

1. Prefer correctness and simplicity over cleverness.
2. Keep APIs small and unsurprising.
3. Keep naming and formatting idiomatic and consistent.
4. Optimize only after identifying a measured bottleneck.

## Writing Guidance

Use the checklist in `references/rules.md` as the source of truth during implementation and review.
