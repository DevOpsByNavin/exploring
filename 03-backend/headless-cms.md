- Traditional CMS (*WordPress*): content + design/templates live together. You write content and the CMS also decides how the site looks.
- Headless CMS: you manage structured content only. No opinion on display — content goes out via API (REST or GraphQL).

> A headless CMS is a content engine: a friendly dashboard for writing text, uploading images, and managing data, then an API serving that content.

## What to choose

### Strapi

- Built on Node.js, self-hostable (or Cloud).
- GUI-first. Standard REST/GraphQL APIs; full data ownership.

### Sanity

- Structured content, flexible, real-time collaboration.
- Editing UI (Sanity Studio) is a customizable React app.
- Uses its own query language (**GROQ**).
- **Best for:** portfolios, marketing sites, complex blogs, highly structured reusable content.

### Payload CMS

- TypeScript-native, code-first (schema + admin UI defined in code).
- Runs as standalone Express app or embedded in `Next.js`.

### Directus

- Database-first: wraps an existing/new SQL database (PostgreSQL/MySQL) with instant APIs + admin UI.

### Storyblok

- Visual component-based editing with real-time preview for marketing teams.

### Contentful

- Enterprise-grade, restrictive free tier. Complex roles, audit logs, localization.

## Comparison

| CMS | Type | Schema style | Best for | Avoid if |
| --- | --- | --- | --- | --- |
| **Strapi** | Open-source (self-hosted or Cloud) | GUI-first (dashboard) | Standard REST/GraphQL APIs; teams wanting infra + data ownership. | You refuse to run a Node runtime/DB or need native visual canvas editing. |
| **Sanity** | Hosted SaaS (local or hosted Studio) | Code-first (JS/TS) | Complex structured data, programmatic migrations, editor collaboration. | You want zero lock-in or refuse proprietary tooling/GROQ. |
| **Payload CMS** | Open-source (self-hosted or Cloud) | Code-first (TypeScript) | Full-stack Next.js/Node with end-to-end type safety. | Non-technical users must define schema themselves. |
| **Directus** | Open-source (self-hosted or Cloud) | Database-first | Wrapping raw SQL with instant APIs + admin UI. | You prefer document modeling or don't want SQL. |
| **Storyblok** | Hosted SaaS | GUI-first (visual) | Component-based visual editing with live preview. | You want presentation-agnostic raw content only. |
| **Contentful** | Hosted SaaS | GUI-first (dashboard) | Enterprise roles, audit logs, localization. | Indie budget or code-based schema requirement. |

Chooser: need visual preview → Storyblok; existing SQL → Directus; code-first Next.js → Payload; cheap + own data → Strapi; complex structured content → Sanity. Check webhooks, preview, localization, and free-tier caps before committing.
