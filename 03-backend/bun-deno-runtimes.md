## Bun

Like **Node.js**, a JS/TS runtime. Its runtime is **written in** Zig (Deno's is written in Rust).

Aims to replace:
- Runtime: **Node.js** / **Deno**
- Package manager: **npm**
- Test runner: **Jest**
- Bundler: **Webpack**, **Vite**

### Node.js vs Bun

| Aspect | Node.js | Bun |
| --- | --- | --- |
| JS engine | V8 (Chrome's) | JavaScriptCore (Safari's) — faster startup, lower memory |
| Implemented in | C++ | Zig |
| Scope | Runtime only | All-in-one — runtime + package manager + test runner + bundler |
| TypeScript | Via build tools (native type-stripping in recent versions) | Native |
| Package manager | npm (separate install, slower) | Built-in `bun install`, npm-compatible, much faster |
| Startup speed | Slower cold start (heavier runtime) | Faster cold start (slim runtime + JSC) |
| Extra built-ins | `fs`, `http`, etc. | Plus `Bun.serve`, `bun:sqlite`, `Bun.$` shell, `.env` auto-load |
| Compatibility | The standard — everything targets it | Drop-in goal, npm-compatible, edge cases exist |
| Maturity | Battle-tested since 2009 | Gaining fast, still younger |

## Deno

- By the creator of **Node.js**. Deno 2 added npm compatibility (`npm:` specifiers, `package.json` support).
- The Deno **company** restructured in 2025 (layoffs, pivot) — future is uncertain, but the runtime is MIT open-source and maintained. Prefer Node/Bun for new work unless you specifically need Deno Deploy / JSR.
