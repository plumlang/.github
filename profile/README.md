<div align="center">

<img src="./cover.png" alt="Plumlang" width="100%"/>

# Plumlang

**A small, fast, memory-safe programming language. Easy to write, one binary, runs anywhere.**

An [Elixpo](https://elixpo.com) production.

[Website](https://plum.elixpo.com) · [Documentation](https://plum.elixpo.com/docs/) · [Language](https://github.com/plumlang/plumlang) · [Roadmap](https://github.com/plumlang/plumlang/issues/36) · [Discussions](https://github.com/plumlang/plumlang/discussions)

</div>

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
| [plumlang](https://github.com/plumlang/plumlang) | The language: compiler, virtual machine, standard library, specification, and tests. The main repository. |
| [plum.elixpo](https://github.com/plumlang/plum.elixpo) | The website at [plum.elixpo.com](https://plum.elixpo.com): documentation, guides, and the browser playground. |
| [branding](https://github.com/plumlang/branding) | Logos, icons, colours, and the VS Code extension. |

The three are kept in sync from the main repository: shared CI, deployment
and release workflows, and the documentation the website publishes.

## Releases

Plumlang is in **alpha**. The language and its standard library are complete
for the 1.0 scope; tooling (formatter, REPL, editor support, playground) and
release packaging are in progress.

| Version | Status |
|---|---|
| 1.0 | Planned. Specification frozen for 1.x compatibility, signed builds for every platform. Tracked in [plumlang#35](https://github.com/plumlang/plumlang/issues/35). |
| Pre-releases | Built from `main`; see [Releases](https://github.com/plumlang/plumlang/releases). Installers (`install.sh`, `install.ps1`, Homebrew, winget) arrive with [plumlang#33](https://github.com/plumlang/plumlang/issues/33). |

Until then, build from source in a few seconds:

```bash
git clone https://github.com/plumlang/plumlang
cd plumlang
make
./plum run examples/http/hello.plum
```

## Get involved

- **Contribute:** read [CONTRIBUTING.md](https://github.com/plumlang/plumlang/blob/main/CONTRIBUTING.md). Issues labelled [good first issue](https://github.com/plumlang/plumlang/issues?q=is%3Aopen+label%3A%22good+first+issue%22) are a good start.
- **Ask:** [Discussions](https://github.com/plumlang/plumlang/discussions), or **hello@elixpo.com**.
- **Report a security issue:** follow the [security policy](https://github.com/plumlang/plumlang/blob/main/docs/SECURITY.md).

## Licence

Plumlang is source-available under the
[Plumlang Commercial License 1.0](https://github.com/plumlang/plumlang/blob/main/LICENSE):
free for personal, educational, research and other non-commercial use, and to
evaluate for 60 days. Commercial use needs a licence: **hello@elixpo.com**.
Programs you write in Plumlang are yours.

---

<div align="center"><sub>© 2026 Elixpo. Plumlang and the Plumlang logo are trademarks of Elixpo.</sub></div>
