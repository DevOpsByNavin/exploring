> VUE 3

React diffs everything to find changes; Vue's compiler marks the changes in advance, then diffs only those spots. 

| React (lib) | Vue (framework) |
| - | - |
| component + state | on top of that: folder structure, router, data fetching |

## .vue (Single File Component)

One file contains three different blocks:

1. `<template>` -> html
2. `<script lang="ts>` -> ts
3. `<style>` -> css


## VDOM but smarter

Vue's compiler pre-analyzes the template at build time and bakes hints into the render function:

  - Static hoisting — content that never changes (most of your markup) is created once and skipped during diffs entirely.
  - Patch flags — the compiler marks exactly which parts can change: "only the text inside this button is dynamic; its attributes never change." At runtime, diffing skips everything else.
  - Block tree — dynamic nodes are flattened into a flat list, so diffing skips the static structure.

>  Vue moved part of the diffing cost to build time 

## How it works

```
State changes
   → re-run the component's render function (same as React)
   → build new VDOM — BUT: static nodes are hoisted (created once, reused, not rebuilt, not diffed)
   → diff ONLY the "dynamic nodes list" — a flat array the compiler prepared
   → patch real DOM
```


Vue's compiler pre-analyzed the template and produced a `block` tree: it flattened all potentially-dynamic nodes into a short list, skipping over all the static structure entirely. So the runtime diff isn't walking the whole tree — it walks a flat array of, say, 3 dynamic nodes instead of 300 total nodes.
