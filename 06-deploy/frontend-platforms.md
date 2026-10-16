## Vercel

- Team behind `Next.js`. Default for React/Next.js (also serves Vue/Svelte).
- Free `.vercel.app` domain, preview deployments per PR.
- SSR + edge/serverless functions built in.

## Netlify

- Similar to Vercel (deploys, forms, identity, functions). Historically stronger on static + Jamstack.

## Cloudflare Pages

- Static hosting + Pages Functions for light server logic. Generous free bandwidth; pairs with Workers/D1/R2.

## GitHub Pages

- Static-only (no SSR, no functions). Free for public repos; fine for docs/demos.

> Vercel / Netlify / Cloudflare Pages also offer compute — don't confuse static hosting with it.

| Entry | Category | What it really is |
| --- | --- | --- |
| Cloudflare Pages | Static hosting + optional functions | Static assets + lightweight logic |
| Netlify | Frontend platform + serverless | Frontend apps + functions/forms |
| Vercel | Frontend cloud + managed compute | Static, SSR, functions, full-stack frameworks |
| Cloudflare Workers | Compute, not a host | Request handlers, APIs, cron, static assets via bindings |

Chooser: SSR + previews → Vercel; static + bandwidth → Cloudflare Pages; docs/demos → GitHub Pages. Check build minutes, bandwidth, and SSR support caps.
