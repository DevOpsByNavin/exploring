> Vue 3

React diffs the whole subtree to find changes; Vue's compiler marks what can change in advance, then diffs only those spots.

| React (library) | Vue (framework ecosystem) |
| --- | --- |
| component + state (`react`, `react-dom`) | same core idea, plus official router (`vue-router`) and store (`pinia`); full app = Vue + Nuxt |

Use when: you want React-like components with more built-in conventions and less manual memoization.

## `.vue` (Single File Component)

One file, three blocks:

1. `<template>` -> HTML
2. `<script setup lang="ts">` -> TS (Composition API, the default in Vue 3)
3. `<style scoped>` -> CSS (scoped to this component unless unscoped)

`ref` vs `reactive`: `ref<number>(0)` needs `.value` in script, auto-unwraps in template. `reactive` is for objects only.

## VDOM but smarter

Vue's compiler pre-analyzes the template at build time and bakes hints into the render function:

- Static hoisting — content that never changes is created once and skipped during diffs entirely.
- Patch flags — the compiler marks exactly what can change: "only the text inside this button is dynamic." At runtime, diffing skips everything else.
- Block tree — dynamic nodes are flattened into a flat list, so diffing skips the static structure.

> Vue moved part of the diffing cost to build time

## How it works

```
State changes
   → re-run the component's render function (same as React)
   → build new VDOM — BUT: static nodes are hoisted (created once, reused, not rebuilt, not diffed)
   → diff ONLY the "dynamic nodes list" — a flat array the compiler prepared
   → patch real DOM
```

Example: a 300-node template with 3 dynamic bits diffs a flat array of 3 nodes, not the whole tree.
