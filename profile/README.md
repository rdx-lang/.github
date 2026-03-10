# RDX (Reactive Document eXpressions)

**A strictly typed, declarative document format for rich, interactive content.**

RDX extends CommonMark with components, typed attributes, and structured data — without executing code. Documents are pure data: parse them into a typed AST from Rust, Node.js, Python, or the browser.

## Why RDX

- **No runtime, no execution** — Components describe *what* to render, never *how*. No `import`, no `eval()`, no JavaScript in your documents.
- **Runs anywhere** — One parser, every platform. Native bindings for Rust, Node.js, and Python. WebAssembly for browsers and edge runtimes.
- **Schema validation** — Define what components exist, what props they accept, and catch errors at build time — not in production.
- **Formally specified** — The [specification](https://github.com/rdx-lang/rdx/blob/main/SPECIFICATION.md) defines every construct and its AST output. Predictable, deterministic, no implementation-defined behavior.
- **AI-ready** — Clean text extraction for RAG pipelines, embeddings, and search indexing. No JSX artifacts polluting your vectors.

## Quick look

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

## Get started

```sh
cargo add rdx-parser    # Rust
pip install rdx-parser          # Python
npm install @rdx-lang/node  # Node.js
npm install @rdx-lang/wasm  # Browser / Deno / Edge
```

## Repositories

### [`rdx`](https://github.com/rdx-lang/rdx) — Parser & Toolchain

The core Rust implementation with bindings for every platform.

| Crate | What it does |
|---|---|
| `rdx-parser` | Parses `.rdx` into a spec-compliant AST |
| `rdx-ast` | AST type definitions |
| `rdx-schema` | Component schema validation |
| `rdx-transform` | Composable AST transforms (auto-slug, TOC) |
| `rdx-github` | GitHub references transform |
| `rdx-wasm` | WebAssembly bindings |
| `rdx-node` | Native Node.js bindings |
| `rdx-py` | Python bindings |

### [`rdx-js`](https://github.com/rdx-lang/rdx-js) — JavaScript Ecosystem

Pure TypeScript packages for the JS ecosystem.

| Package | What it does |
|---|---|
| `@rdx-lang/types` | TypeScript type definitions for the AST |
| `@rdx-lang/core` | JS transform pipeline, tree walking, utilities |
| `@rdx-lang/github` | GitHub references transform (pure JS) |

### [`tree-sitter-rdx`](https://github.com/rdx-lang/tree-sitter-rdx) — Editor Support

Syntax highlighting and structural analysis for Neovim, Helix, Zed, and any tree-sitter-compatible editor.

## Links

- [Specification](https://github.com/rdx-lang/rdx/blob/main/SPECIFICATION.md)
- [Rust Docs](https://github.com/rdx-lang/rdx)
- [JavaScript Packages](https://github.com/rdx-lang/rdx-js)
- [Tree-sitter Grammar](https://github.com/rdx-lang/tree-sitter-rdx)
