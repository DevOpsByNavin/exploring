`React` and `Vue` ship a runtime and your components as data; watches state and patch DOM at runtime (vdom + diff); Svelte shifts that work to build time: the compiler turns your component into vanilla JS that directly updates the exact DOM node. No vdom, no runtime diff library in the bundle — just tiny generated update code.

> The reactivity graph is constructed at compile time, not discovered at runtime. This is the deepest difference from both React (runtime diffing) and Vue (runtime proxy tracking).

- React: re-execute component → diff subtree → patch. Bundle includes react-dom.
- Vue: ref mutates → compiler-flagged vdom patch. Bundle includes Vue runtime.
- Svelte: let count = 0; count++ → compiler already generated button.textContent = ... update. Bundle is just your code + tiny helpers.

> File extension: `.svelte`

## .svelte (Single File Component)

One file contains three different blocks:

1. `html` -> anything outside `script and stype` tag
2. `<script lang="ts>` -> ts
3. `<style>` -> css
