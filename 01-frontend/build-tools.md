## What it does

- JSX/TSX -> JS
- TS -> JS (type-stripping / transpile)
- Bundles files into an optimized package (code-split, minified, hashed)

## Vite

- Default for new frontend projects. Framework-agnostic (React / Vue / Svelte).
- Dev: esbuild transform + HMR — browser updates instantly on save, preserving component state where possible. No bundle in dev.
- Build: Rollup bundles + minifies for production.
- Plugins add framework support (`@vitejs/plugin-react`, `@vitejs/plugin-vue`, `@sveltejs/vite-plugin-svelte`) and Tailwind.

Alternatives: Turbopack (Next.js), Rspack (webpack-compatible, Rust). Vite won on speed + plugin ecosystem.
