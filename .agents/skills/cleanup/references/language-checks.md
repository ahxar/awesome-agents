# Language Checks And Best Practices

Use this reference during the cleanup workflow after a feature is implemented.

## Universal order

1. Run project-native commands first (package scripts, Makefile, justfile, CI config).
2. Run formatter/linter before tests when formatting noise is likely.
3. Run focused tests for touched modules, then full suite only when risk justifies it.
4. Keep behavior stable; cleanup should improve quality, not rewrite features.

## JavaScript And TypeScript

- Format: `prettier --write` (or project formatter command).
- Lint: `eslint`.
- Types: `tsc --noEmit` (for TypeScript).
- Tests: `vitest`, `jest`, or project test command.
- Best practices:
  - Remove `console.log` debug noise unless intentionally kept.
  - Remove unused imports/variables.
  - Prefer consistent async error handling and avoid swallowed rejections.
  - Keep React/UI cleanup aligned with existing component patterns.

## Python

- Format: `ruff format` or `black`.
- Lint: `ruff check` (or `flake8` if used).
- Types: `mypy` or `pyright` if configured.
- Tests: `pytest`.
- Best practices:
  - Remove dead branches and broad `except Exception` when unnecessary.
  - Keep function responsibilities small and explicit.
  - Preserve clear docstrings for non-obvious behavior.

## Go

- Format: `gofmt -w` or `go fmt ./...`.
- Lint: `golangci-lint run` if present.
- Build/tests: `go test ./...`.
- Best practices:
  - Return wrapped errors with context.
  - Keep package boundaries clear; avoid over-abstracting small features.
  - Remove stale exported symbols and keep naming idiomatic.

## Rust

- Format: `cargo fmt`.
- Lint: `cargo clippy -- -D warnings` when the project expects strict linting.
- Tests: `cargo test`.
- Best practices:
  - Remove unnecessary clones and unused lifetimes/types.
  - Prefer explicit error propagation with context.
  - Keep module visibility minimal (`pub` only when needed).

## Java And Kotlin

- Format/lint: project-native tools (`spotless`, `ktlint`, `checkstyle`, `detekt`).
- Build/tests: `./gradlew test` or `mvn test`.
- Best practices:
  - Keep null handling explicit.
  - Avoid duplicated business logic across services/classes.
  - Remove unused fields/methods created during development.

## C# And .NET

- Format: `dotnet format` when configured.
- Build: `dotnet build`.
- Tests: `dotnet test`.
- Best practices:
  - Keep async flows consistent (`async/await` end-to-end when needed).
  - Remove dead DI registrations and unused services.
  - Keep exceptions specific and meaningful.

## Ruby

- Format/lint: `rubocop` (or project wrapper).
- Tests: `rspec` or `minitest`.
- Best practices:
  - Remove stale callbacks and unused concerns.
  - Keep service objects and models focused.
  - Avoid hidden side effects in cleanup refactors.

## PHP

- Format: `php-cs-fixer` or `pint` (Laravel).
- Lint/static analysis: `phpstan` or `psalm`.
- Tests: `phpunit` or `pest`.
- Best practices:
  - Remove unused container bindings and helper functions.
  - Keep request/response validation clear and centralized.
  - Avoid silent failure paths in exception handling.

## C And C++

- Format: `clang-format`.
- Static checks: `clang-tidy` or project compiler warnings.
- Build/tests: project build system (`cmake`, `make`, etc.).
- Best practices:
  - Remove unused macros, includes, and dead branches.
  - Strengthen boundary checks and error paths.
  - Keep ownership and lifetime handling explicit.

## Swift

- Format/lint: `swift-format` or `swiftlint` if configured.
- Build/tests: `xcodebuild test` or `swift test`.
- Best practices:
  - Keep optional handling explicit and safe.
  - Remove stale state and debug code in view models/controllers.
  - Keep async tasks cancel-safe where relevant.
