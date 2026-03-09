# Contributing to RDX

Thanks for your interest in contributing to RDX. This guide applies to all repositories under the `rdx-lang` organization.

## Getting Started

1. Fork the repository
2. Create a branch from `main`
3. Make your changes
4. Run the test suite
5. Open a pull request

## Development Setup

### `rdx` (Rust parser and toolchain)

```sh
git clone https://github.com/rdx-lang/rdx.git
cd rdx
cargo test
```

### `tree-sitter-rdx` (Tree-sitter grammar)

```sh
git clone https://github.com/rdx-lang/tree-sitter-rdx.git
cd tree-sitter-rdx
bunx tree-sitter generate
bunx tree-sitter test
```

## What to Work On

- Check [open issues](https://github.com/rdx-lang/rdx/issues) for tasks labeled `good first issue` or `help wanted`
- Spec clarifications and wording improvements
- New AST transforms via the `Transform` trait
- Parser bug fixes with a failing test case
- Tree-sitter grammar improvements and new corpus tests
- Bindings for other languages (Python, Node.js, Go, etc.)

## Pull Requests

- Keep PRs focused — one concern per PR
- Include tests for new behavior or bug fixes
- Reference the relevant spec section when applicable
- Ensure `cargo test` (or `tree-sitter test`) passes before submitting

## Spec Changes

Changes to `SPECIFICATION.md` require discussion before implementation. Open an issue describing the motivation, proposed syntax, and AST impact. Non-trivial spec changes should include:

- A clear use case
- Example `.rdx` input and expected AST output
- Consideration of backward compatibility

## Code Style

- Rust: follow standard `rustfmt` conventions
- Tree-sitter: follow existing grammar.js patterns
- Prefer clarity over cleverness
- Add comments only where the logic isn't self-evident

## Reporting Bugs

Use the [bug report template](https://github.com/rdx-lang/.github/issues/new?template=bug_report.yml) and include:

- RDX input that reproduces the issue
- Expected vs actual AST output
- Version of the parser or grammar

## License

By contributing, you agree that your contributions will be licensed under the same license as the project.
