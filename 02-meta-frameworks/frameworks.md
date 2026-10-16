## Next.js

- Built by Vercel, runs on top of React.

**Working**

- Uses React Server Components (RSC). Default is a Server Component (runs only on server, e.g. data fetching, sends HTML).
- Mark interactive parts with `'use client'` — only those get a JS bundle for the browser.

## Nuxt

- Mature, polished framework for **Vue**.
- Uses the **Nitro** engine — same code deploys to Node, Vercel, Netlify, Cloudflare (e.g. `nitro preset: cloudflare-pages`).

## Astro

- Framework-agnostic (mix React / Vue / Svelte in one page).
- For content-heavy sites. Zero JS by default.

**Working**

- Uses its own Astro Component Syntax (`*.astro`) for static UI.
- For interactive UI, drop a framework component in as an "island" — Astro hydrates only that island, rest stays pure HTML.

> Avoid if the product is a highly interactive SaaS (islands overhead adds up).

## SvelteKit

- Built on Svelte. Clean, simple, minimal.

**Working**

- Svelte compiler turns components into tiny JS at build time.
- Uses "adapters" (`adapter-node`, `adapter-vercel`, `adapter-cloudflare`) — pick the deploy target and it formats the output accordingly.

> Smaller ecosystem than Next/Nuxt, but best DX for Svelte fans.
