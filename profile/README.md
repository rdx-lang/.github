# RDX (Reactive Document eXpressions)

**A strictly typed, declarative document format for rich, interactive content.**

RDX extends CommonMark with components, typed attributes, and structured data — without executing code. Documents are pure data: parse them into a typed AST from Rust, Node.js, Python, or the browser.

## Why RDX

- **No runtime, no execution** — Components describe _what_ to render, never _how_. No `import`, no `eval()`, no JavaScript in your documents.
- **Runs anywhere** — One parser, every platform. Native bindings for Rust, Node.js, and Python. WebAssembly for browsers and edge runtimes.
- **Schema validation** — Define what components exist, what props they accept, and catch errors at build time — not in production.
- **Formally specified** — The [specification](https://github.com/rdx-lang/rdx/blob/main/SPECIFICATION.md) defines every construct and its AST output. Predictable, deterministic, no implementation-defined behavior.
- **AI-ready** — Clean text extraction for RAG pipelines, embeddings, and search indexing. No JSX artifacts polluting your vectors.

## Quick look

```rdx
---
title: Getting Started
---

# {$title}

<Notice type="warning" dismissible>
  This API is in beta. See the [migration guide](/docs/migrate).
</Notice>
```

## Get started

```sh
cargo add rdx-parser           # Rust
pip install rdx-parser         # Python
npm install @rdx-lang/node     # Node.js
npm install @rdx-lang/wasm     # Browser / Deno / Edge
cargo install rdx-cli          # CLI
```

## Repositories

| Repo                                                             | Description                                                              |
| ---------------------------------------------------------------- | ------------------------------------------------------------------------ |
| [`rdx`](https://github.com/rdx-lang/rdx)                         | Parser, schema, transforms, bindings (Rust, Node, Python, WASM), and CLI |
| [`rdx-js`](https://github.com/rdx-lang/rdx-js)                   | TypeScript types, JS transform pipeline, and JS-native extensions        |
| [`tree-sitter-rdx`](https://github.com/rdx-lang/tree-sitter-rdx) | Syntax highlighting for Neovim, Helix, Zed                               |

## Links

- [Specification](https://github.com/rdx-lang/rdx/blob/main/SPECIFICATION.md)
- [JavaScript Packages](https://github.com/rdx-lang/rdx-js)
- [Tree-sitter Grammar](https://github.com/rdx-lang/tree-sitter-rdx)
