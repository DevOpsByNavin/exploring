TS = JS + static types
- `tsc` (using `tsconfig.json`) type-checks, then strips types to emit pure JS. Types never run in the browser.

Tailwind CSS = utility classes used directly in HTML
- The build scans your files and generates only the utilities you used into one CSS file.

## Modular API-driven frontend

- Vanilla stack

  You tell the browser how to update the DOM step by step.
  Con: even a small change can mean touching lots of elements by hand.

- Modern libraries / frameworks

  You describe what the page should look like for a given state; the library figures out the DOM updates.

### React

```
1. You click the button
        │
2. setLikes(6) schedules a re-render (React does not "watch" state)
        │
3. React RE-RUNS your component function:
   LikeButton() executes again → returns React elements
        │
4. New elements → new virtual DOM tree (cheap JS objects, Fiber nodes)
        │
5. React DIFFS the new tree vs the old tree:
   "button → same; text child changed 5 → 6"
   Comparing two JS objects is FAST.
        │
6. React applies ONLY the detected differences
   to the real DOM: textNode.data = "❤️ 6"
   (one surgical real-DOM write, not a page rebuild)
        │
7. Browser repaints just that bit
```
> virtual DOM = cheap JS object describing the real DOM

How it works in 3 steps:
1. You say where React lives: `<div id="react-root">`
2. You say what it looks like: a `ReactButton` component
3. `setState` triggers a re-render; React diffs and patches only what changed

Split to know: `react` (component model) + `react-dom` (browser renderer).

**SPA**
- Server sends near-empty `index.html` + JS bundle.
- Client executes JS to render interactive UI.
- Tradeoff: blank first paint, weak SEO, hydration cost. That's why meta-frameworks exist.

**Vite**
- Dev (`npm run dev`): esbuild transforms + HMR (state-preserving instant update), no bundle.
- Build (`npm run build`): Rollup produces the optimized bundle.
- JSX/TSX -> JS. Tailwind -> CSS via the Tailwind Vite plugin / PostCSS, not Vite core.
