# Security Policy

## Reporting a Vulnerability

If you discover a security vulnerability in any `rdx-lang` repository, please report it responsibly.

**Do not open a public issue.** Instead, email security concerns to the project maintainers or use [GitHub's private vulnerability reporting](https://docs.github.com/en/code-security/security-advisories/guidance-on-reporting-and-writing-information-about-vulnerabilities/privately-reporting-a-security-vulnerability).

We aim to acknowledge reports within 48 hours and provide a fix or mitigation plan within 7 days.

## Scope

This policy covers:

- `rdx` — the Rust parser and toolchain
- `tree-sitter-rdx` — the tree-sitter grammar
- Any other repository under the `rdx-lang` organization

## Design Philosophy

RDX is designed to be safe by default. Documents are declarative data — there is no code execution, no `import` statements, and no eval. The parser produces a typed AST with no side effects. This is a core security property of the format.
