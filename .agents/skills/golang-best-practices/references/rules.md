# Go Rules Checklist

Use this checklist while writing or reviewing code. Tags show primary source:

- `[EG]` Effective Go
- `[CRC]` Go Code Review Comments
- `[UB]` Uber Go Style Guide

## Source Documents

- [Effective Go](https://go.dev/doc/effective_go)
- [Code Review Comments](https://go.dev/wiki/CodeReviewComments)
- [Uber Go Style Guide](https://github.com/uber-go/guide/blob/master/style.md)

## 1) Formatting and File Layout

- Run `gofmt` on all changed Go files. Do not hand-format. `[EG][CRC]`
- Keep files focused by package responsibility; avoid mixed concerns. `[EG]`
- Prefer early returns over nested conditionals when behavior is equivalent. `[EG][UB]`

## 2) Naming and Documentation

- Use short, lowercase package names with no underscores or mixed caps. `[EG]`
- Avoid repeating package names in exported identifiers (`http.Server`, not `http.HTTPServer`). `[EG]`
- Use concise receiver names (`c`, `s`, `r`) and keep them consistent per type. `[CRC]`
- Preserve common initialisms in all caps (`ID`, `URL`, `HTTP`, `JSON`). `[UB]`
- Add doc comments for exported identifiers; start with the identifier name. `[EG][CRC]`

## 3) Error Handling

- Treat errors as values; return and wrap them instead of using panic for normal flow. `[EG][UB]`
- Use `%w` for wrapping and rely on `errors.Is` / `errors.As` at call sites. `[UB]`
- Keep error strings lowercase and without trailing punctuation unless required. `[CRC][UB]`
- Handle each error once; avoid duplicate log+return chains unless intentional. `[UB]`
- Avoid blank identifier for errors except when explicitly safe and documented. `[EG][CRC]`

## 4) Interfaces and API Design

- Define interfaces where they are consumed, not where they are produced. `[CRC][UB]`
- Keep interfaces minimal; prefer concrete types until abstraction is needed. `[EG][CRC]`
- Do not use pointers to interfaces. `[UB]`
- Make zero values useful where practical; require constructors only when needed. `[EG]`
- Use compile-time interface assertions when conformance must be explicit. `[UB]`
- Prefer functional options only when constructors need optional, extensible configuration. `[UB]`

## 5) Concurrency and Context

- Make goroutine lifecycles explicit; avoid fire-and-forget unless clearly bounded. `[UB]`
- Wait for started goroutines to finish on shutdown/test completion. `[UB]`
- Pass `context.Context` as the first parameter for request-scoped work. `[CRC]`
- Never store context in structs; propagate it through call chains. `[CRC]`
- Use synchronization primitives intentionally; prevent data races by design. `[EG][UB]`

## 6) Collections, Allocation, and Performance

- Avoid premature optimization; profile first. `[EG]`
- Preallocate slices/maps when size is known and measurable. `[UB]`
- Prefer `bytes.Buffer` or `strings.Builder` for repeated string assembly. `[EG][UB]`
- Prefer `strconv` over `fmt` in hot numeric/string conversion paths. `[EG]`
- Copy slices/maps at API boundaries when retaining mutable caller-owned data. `[UB]`

## 7) Testing and Review Quality

- Keep tests deterministic and isolated; avoid timing-dependent sleeps when possible. `[CRC][UB]`
- Prefer table-driven tests for sets of behavior variants. `[CRC]`
- Verify both happy paths and edge/error paths for public behaviors. `[UB]`
- Keep helper functions small and focused; reduce hidden test coupling. `[UB]`

## 8) Review Output Expectations

- Call out violations with concrete file and line references.
- Explain why each change improves clarity, safety, or maintainability.
- Keep edits minimal and scoped to the requested task.
