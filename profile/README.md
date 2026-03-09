# RDX (Reactive Document eXpressions)

**A strictly typed, declarative document format for rich documents.**

RDX is a superset of CommonMark that adds interactive components, strictly-typed attributes, and structured data. It produces a clean, predictable AST that any language or framework can consume — no runtime, no bundler, no JavaScript required.

## Who is RDX for?

- **Platform teams** shipping docs infrastructure where arbitrary JS execution is a security risk
- **Rust, Go, Python backends** that need rich component documents without a Node.js dependency
- **CMS and tooling authors** who want a spec-driven format with a guaranteed AST shape, not implementation-defined behavior
- **Teams at scale** where documents are data — validated, transformed, and rendered by pipelines, not dev servers

If you're a solo developer happy with MDX and its ecosystem, MDX is great. RDX exists for the cases where you need **safety without sandboxing**, **portability across language runtimes**, and **a formal specification** you can build contracts around.

## What makes RDX different

**No runtime, no execution** — An RDX document is pure data. Components describe *what* to render, never *how*. There is no `import`, no function calls, no expression evaluation. The parser output is a typed AST that renderers consume directly.

**Runs anywhere** — The reference parser is written in Rust. There is no dependency on Node.js or any JavaScript toolchain. Embed it in a CLI, a server, a WASM module, or a mobile app.

**Formally specified** — The [specification](https://github.com/rdx-lang/rdx/blob/main/SPECIFICATION.md) defines every syntactic construct and its AST output. Multiple parser implementations can exist and produce identical results.

**Batteries included** — Frontmatter, GFM extensions (tables, strikethrough, task lists, footnotes), LaTeX math, and HTML pass-through are all part of the core grammar. No plugins needed for the common cases.

**Extensible by design** — The `Transform` trait provides a composable pipeline for AST-level transforms (auto-slug, table of contents, custom link rewriting). Add what you need, skip what you don't.

## Quick Look

```rdx
---
title: Getting Started
version: 1.0
---

# {$title}

<Notice type="warning" dismissible>
  This API is in beta. See the [migration guide](/docs/migrate).
</Notice>

<Card title="Installation" icon={$config.installIcon}>
  Run `npm install @example/sdk` to get started.
</Card>

The equation $E = mc^2$ changed everything.
```

## Repositories

### [`rdx`](https://github.com/rdx-lang/rdx) — Reference Implementation

The official Rust parser and toolchain.

- **`rdx-parser`** — Full RDX parser producing a spec-compliant AST
- **`rdx-ast`** — AST types with serialization support
- **`rdx-transform`** — Composable AST transform pipeline (auto-slug, table of contents, and custom transforms)
- **`rdx-github`** — Optional GitHub references transform (`#123`, `@user`, commit SHAs)

### [`tree-sitter-rdx`](https://github.com/rdx-lang/tree-sitter-rdx) — Tree-sitter Grammar

Syntax highlighting and structural analysis for editors. Powers RDX support in Neovim, Helix, Zed, and any tree-sitter-compatible editor.

## Links

- [Specification](https://github.com/rdx-lang/rdx/blob/main/SPECIFICATION.md)
- [Rust Crate Documentation](https://github.com/rdx-lang/rdx)
- [Tree-sitter Grammar](https://github.com/rdx-lang/tree-sitter-rdx)
