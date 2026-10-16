## Next.js

- built by Vercel
- runs on top of React

**Working**

- It uses React Server Component (RSC)
- Next.js allow to mark component as "Server Component"
- These component runs only on server for something like fetching data
- And sends pure HTML to browser
- Client then download js bundle only for interactive client component

## Nuxt

- mature, polished framework for **Vue**
- uses **Nitro** engine - can be deployed anywhere

## Astro

- framework agnostic (mix-match any UI)
- target content heavy site
- load balzingly fast with zero JS

**Working**

- Uses it's own Astro Component Syntax (*.astro*) for simple UI
- For complex interactive UI, you can drop specific component into page as an "Island"
- Astro only hydrates that island, leaving rest of page as pure HTML.

> Avoid if goal product is highly interactive SaaS

## SvelteKit

- build on Svelte
- clean, simple and minimal

**Working**

- Being a compiler, it turns component onto tiny JS file during build step
- Uses "Adapter"; just tell where to deploy it, then it will format build output accordingly

> Niche, better DX
