<div align="center">

<a href="https://plum.elixpo.com"><img src="./banner.jpg" alt="Elixpo x Plumlang: a new programming language, built in the open" width="100%"/></a>

# Plumlang

**Reads like English. Runs fast. Ships as one binary.**

A statically typed, memory-safe programming language written in C, from [Elixpo](https://elixpo.com), built in the open.

</div>

<p align="center">
  <a href="https://plum.elixpo.com"><img alt="Website" src="https://img.shields.io/badge/Website-plum.elixpo.com-6b3fa0?style=for-the-badge&logo=googlechrome&logoColor=white"></a>
  <a href="https://plum.elixpo.com/docs/"><img alt="Documentation" src="https://img.shields.io/badge/Docs-read_the_guide-6b3fa0?style=for-the-badge&logo=readthedocs&logoColor=white"></a>
  <a href="https://plum.elixpo.com/playground/"><img alt="Playground" src="https://img.shields.io/badge/Playground-try_it_now-ff7a59?style=for-the-badge&logo=webassembly&logoColor=white"></a>
  <a href="https://plum.elixpo.com/docs/install/"><img alt="Install" src="https://img.shields.io/badge/Install-one_command-24292f?style=for-the-badge&logo=gnubash&logoColor=white"></a>
</p>

<p align="center">
  <a href="https://github.com/plumlang/plumlang/actions/workflows/build.yml"><img alt="Build" src="https://github.com/plumlang/plumlang/actions/workflows/build.yml/badge.svg?branch=main"></a>
  <a href="https://github.com/plumlang/plumlang/releases/latest"><img alt="Release" src="https://img.shields.io/github/v/release/plumlang/plumlang?style=flat-square&label=release&color=6b3fa0"></a>
  <a href="https://github.com/plumlang/plumlang/blob/main/LICENSE"><img alt="Licence: Apache-2.0" src="https://img.shields.io/badge/licence-Apache--2.0-6b3fa0?style=flat-square"></a>
  <a href="https://marketplace.visualstudio.com/items?itemName=plum-lang.plum-lang"><img alt="VS Code extension" src="https://img.shields.io/badge/VS_Code-extension-007acc?style=flat-square&logo=data:image/svg%2bxml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI+PHBhdGggZmlsbD0id2hpdGUiIGQ9Ik0xNyAyIDcgMTEgMyA4IDEgOXY2bDIgMSA0LTMgMTAgOSA0LTJWNHoiLz48L3N2Zz4="></a>
  <a href="https://github.com/plumlang/plumlang/discussions"><img alt="Discussions" src="https://img.shields.io/badge/discussions-join-24292f?style=flat-square&logo=github"></a>
</p>

---

## About

Plumlang is a statically typed programming language with a syntax that reads
like plain English, written from scratch in C11. Programs compile to typed
bytecode and run on a small virtual machine. Memory is managed by reference
counting with copy-on-write values: no garbage collector, no pauses, no manual
freeing.

```plum
seed net.http

plant app = http.server()
app.get("/hello/:name", (req) => http.text("Hello, {req.params["name"]}!"))
app.listen(8080)
```

## What it offers

| | |
|---|---|
| **Easy to read and write** | A small keyword set (`plant`, `branch`, `tree`, `seed`) and error messages that point at the problem and say how to fix it. |
| **Safe by construction** | Static types with inference, optionals instead of null crashes, bounds-checked collections, and a runtime that programs cannot corrupt. |
| **Complete** | Functions and closures, classes and traits, kinds and `match`, modules, error handling, JSON, files, sockets, TLS, and an HTTP server and client. |
| **Concurrent** | Lightweight tasks and channels on an event loop (epoll, kqueue, WSAPoll): thousands of idle connections in a few megabytes. |
| **One binary** | No dependencies to install. The same `plum` runs on Linux, macOS and Windows. |

## Repositories

| Repository | Contents |
|---|---|
| [plumlang](https://github.com/plumlang/plumlang) | The language: compiler, virtual machine, standard library, language server, specification, and tests. The main repository. |
| [plum.elixpo](https://github.com/plumlang/plum.elixpo) | The website at [plum.elixpo.com](https://plum.elixpo.com): documentation, packages, and the browser playground. |
| [registry](https://github.com/plumlang/registry) | Orchard, the package index behind `plum add` and `plum publish`. |
| [branding](https://github.com/plumlang/branding) | Logos, icons, colours, and the VS Code extension. |
| [tree-sitter-plum](https://github.com/plumlang/tree-sitter-plum) | The Tree-sitter grammar, for highlighting in Neovim, Helix, Zed and other editors. |
| [zed-plum](https://github.com/plumlang/zed-plum) | The Zed extension. |
| [highlightjs-plum](https://github.com/plumlang/highlightjs-plum) | highlight.js support, for web pages and docs sites. |
| [pygments-plum](https://github.com/plumlang/pygments-plum) | The Pygments lexer, for Sphinx, MkDocs and Jupyter. |
| [setup-plum](https://github.com/plumlang/setup-plum) | A GitHub Action that installs `plum` in CI. |
| [homebrew-tap](https://github.com/plumlang/homebrew-tap) | The Homebrew formula: `brew install plumlang/tap/plum`. |
| [plum-lang](https://github.com/plumlang/plum-lang) | An earlier tree-walking interpreter in Python, kept as a learning project. |

Shared CI, issue forms and the Elixpo workflows are kept in sync from the
main repository.

## Install

Plumlang **2.2.0** is the current release: eight builds for Linux, macOS and
Windows, with checksums and build attestations on
[Releases](https://github.com/plumlang/plumlang/releases).

```bash
curl -fsSL https://plum.elixpo.com/install.sh | sh          # Linux and macOS
irm https://plum.elixpo.com/install.ps1 | iex               # Windows (PowerShell)
brew install plumlang/tap/plum                              # Homebrew
```

Or try it without installing anything in the
[playground](https://plum.elixpo.com/playground/). To build from source:

```bash
git clone https://github.com/plumlang/plumlang
cd plumlang
make
./plum run examples/http/hello.plum
```

## Packages

| Package | Where |
|---|---|
| Plumlang for VS Code | [VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=plum-lang.plum-lang), [Open VSX](https://open-vsx.org/extension/plum-lang/plum-lang) |
| `@plumlang/tree-sitter-plum` | [npm](https://www.npmjs.com/package/@plumlang/tree-sitter-plum) |
| `@plumlang/highlightjs-plum` | [npm](https://www.npmjs.com/package/@plumlang/highlightjs-plum), [jsDelivr](https://cdn.jsdelivr.net/npm/@plumlang/highlightjs-plum/dist/plum.min.js) |
| `pygments-plum` | [PyPI](https://pypi.org/project/pygments-plum/) |
| `@plumlang/plumlang` (WebAssembly) | [npm](https://www.npmjs.com/package/@plumlang/plumlang) |
| `plum` | [Homebrew tap](https://github.com/plumlang/homebrew-tap): `brew install plumlang/tap/plum` |
| `setup-plum` | GitHub Actions: `uses: plumlang/setup-plum@v1` |

Editors and integrations, with setup steps: [plum.elixpo.com/docs/ecosystem](https://plum.elixpo.com/docs/ecosystem/).

See Plumlang next to other languages on [Rosetta Code](https://rosettacode.org/wiki/Category:Plumlang), starting with [Hello world](https://rosettacode.org/wiki/Hello_world/Text#Plumlang) and [FizzBuzz](https://rosettacode.org/wiki/FizzBuzz#Plumlang), and on [PLDB](https://pldb.io/concepts/plumlang.html).

## Get involved

- **Contribute:** read [CONTRIBUTING.md](https://github.com/plumlang/plumlang/blob/main/CONTRIBUTING.md). Issues labelled [good first issue](https://github.com/plumlang/plumlang/issues?q=is%3Aopen+label%3A%22good+first+issue%22) are a good start.
- **Ask:** [Discussions](https://github.com/plumlang/plumlang/discussions), or **hello@elixpo.com**.
- **Report a security issue:** follow the [security policy](https://github.com/plumlang/plumlang/blob/main/docs/SECURITY.md).

## Licence

Plumlang is licensed under the
[Apache License 2.0](https://github.com/plumlang/plumlang/blob/main/LICENSE):
free to use, change and ship, commercially or not. The
[Plumlang Commercial License](https://github.com/plumlang/plumlang/blob/main/LICENSES/preferred/LicenseRef-Plumlang-Commercial-1.0)
is an option for those who want a written agreement with Elixpo, for
warranty, support or indemnity: **hello@elixpo.com**. Programs you write in
Plumlang are yours.

---

<div align="center"><sub>© 2026 Elixpo. Plumlang and the Plumlang logo are trademarks of Elixpo.</sub></div>
