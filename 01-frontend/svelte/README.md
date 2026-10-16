`React` and `Vue` ship a runtime that re-renders and diffs a virtual DOM at runtime. Svelte shifts that work to build time: the compiler turns your component into vanilla JS that directly updates the exact DOM node. No VDOM, no runtime diff library in the bundle — just tiny generated update code.

> Svelte 5 reactivity is explicit via runes (`$state`, `$derived`, `$effect`), which the compiler turns into surgical updates. This — compile-time reactivity — is the deepest difference from React (re-execute + diff) and Vue (proxy-tracked + flagged diff).

- React: re-execute component → diff subtree → patch. Bundle includes `react-dom`.
- Vue: `ref` mutates → compiler-flagged VDOM patch. Bundle includes Vue runtime.
- Svelte 5: `let count = $state(0); count++` → compiler already generated `button.textContent = ...`. Bundle is just your code + tiny helpers.

> File extension: `.svelte`. Pair with SvelteKit for routing/SSR (the meta-framework).

## `.svelte` (Single File Component)

One file, three blocks:

1. Markup (HTML) — anything outside `script` / `style` tags
2. `<script lang="ts">` — TS + runes (`$state`, `$derived`, `$effect`)
3. `<style>` — CSS, scoped to this component by default
