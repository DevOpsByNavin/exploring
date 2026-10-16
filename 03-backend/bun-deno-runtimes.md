## Bun

Similar to **Node.js**, it is a runtime for JS/TS built on top of **Zig** (Deno is the Rust-based one).

It is build to replace:
- Runtime: **Node.js** or **Deno**
- Package Manager: **npm**
- Test runner: **Jest**
- Bundler: **Webpack**, **Vite**

### Node.js vs Bun

| Aspect | Node.js | Bun |
| --- | --- | --- |
| JS engine | V8 (Chrome's) | JavaScriptCore (Safari's) — faster startup, lower memory |
| Core language | C++ | Rust |
| Scope | Runtime only | All-in-one — runtime + package manager + test runner + bundler |
| TypeScript | Via build tools (native type-stripping recent versions) | Native |
| Package manager | npm (separate install, slower) | Built-in `bun install`, npm-compatible, much faster |
| Startup speed | Slower cold start (heavier runtime) | Faster cold start (slim runtime + JSC) |
| Extra built-ins | `fs`, `http`, etc. | Plus `Bun.serve`, `bun:sqlite`, `Bun.$` shell, `.env` auto-load |
| Compatibility | The standard — everything targets it | Drop-in goal, npm-compatible, but edge cases exist |
| Maturity | Battle-tested since 2009 | Gaining popularity |

## Deno

- By the creator of **Node.js**
- In the verge of shutdown.
