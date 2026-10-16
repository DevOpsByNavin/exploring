TS = JS + type annotation (static type)
- reads tsconfig.json and compiles into pure JS

Tailwind CSS = prebuilt class that is directly used inside HTML
- during compiling; a dedicated `.css` file is created refercing html tag and elements.

## Modular API driven Frontend 

- Vanilla Stack

  Guide browser how to update DOM step by step.  
  Cons being: even for a small change we might need to update tons of page element making it a tedious process.

- With modern library and frameworks

  Instead of guiding browser how to update DOM, we only describe what a page should look like at a given state.

### React

```
1. You click the button
        │
2. setLikes(6) → state changes
        │
3. React RE-RUNS your component function:
   LikeButton() executes again → returns JS object 
        │
4. New JS obj → new virtual DOM tree (cheap JS object)
        │
5. React DIFFS the new tree vs the old tree:
   "button → same; text child changed 5 → 6"
   This comparing of two JS objects is FAST.
        │
  6. React applies ONLY the detected differences
   to the real DOM: textNode.data = "❤️ 6"
   (one surgical real-DOM write, not a page rebuild)
        │
7. Browser repaints just that bit
```
> virtual dom = cheap js object 

How it works in 3 steps:
1. You say where React lives: <div id="react-root">
2. You say what it looks like: ReactButton component
3. React watches the state and updates only what changed


**SPA**
  - server sends empty page (index.html) and js bundle
  - client create a interactive page from that after executing js

**Vite**

During `npm run build` or `npm run dev`; it's the vite that does the job like:

- JSX/TSX -> JS
- Tailwind CSS -> Dedicated CSS file
