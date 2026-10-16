- Traditional CMS (*WordPress*): Content + design/templates live together. You write content and the CMS also decides how the website looks.  
- Headless CMS: You only manage structured content. The CMS has no opinion about how that content is displayed. It just stores the data and gives it out via an API (REST or GraphQL).

> Headless CMS is a  content engine that provides beautiful, user-friendly dashboard for you (or your clients) to write text, upload images, and manage data, and then it spits out that content via an API.

## What to choose

### Strapi

- Built on Node.js/JS & can be self-hosted.

### Sanity

- Strucutured content, flexible, real time collaboration.   
- Provides editing interface (Sanity Studio) which is a React app that can be customized heavily.
- uses it's own query lang (**GROQ**)
- **Best For:** Portfolios, marketing sites, complex blogs, and any project where content needs to be highly structured and reused.

### Payload CMS

- Typescript native, code-first (create schema/UI thorugh code)
- Native to `Next.js` or also run as standalone `Express` app

### Contentful

- Enterprise-Grade with restrictive free tier


## Comparision

| CMS | Type | Schema Style | Best For | Avoid If |
| --- | --- | --- | --- | --- |
| **Strapi** | Open-source (Self-hosted or Cloud) | GUI-first (Dashboard) | Standard REST/GraphQL APIs; teams wanting full infrastructure and data ownership. | You refuse to maintain a Node runtime/DB or require native live visual canvas editing for marketing. |
| **Sanity** | Hosted SaaS (Local or hosted Studio) | Code-first (JS/TS) | Complex structured data, programmatic schema migrations, and deep AI/editor collaboration. | You want zero vendor lock-in or refuse to work with proprietary tooling/GROQ. |
| **Payload CMS** | Open-source (Self-hosted or Cloud) | Code-first (TypeScript) | Full-stack Next.js/Node projects needing end-to-end type safety and config-in-code. | Non-technical users need to define and modify the underlying schema independently. |
| **Directus** | Open-source (Self-hosted or Cloud) | Database-first | Wrapping an existing or new raw SQL database (PostgreSQL/MySQL) with instant APIs and an admin UI. | You prefer pure document-based content modeling or don't want to think in relational SQL tables. |
| **Storyblok** | Hosted SaaS | GUI-first (Visual) | Component-based visual editing where non-technical teams need real-time page previews. | You want strict, presentation-agnostic raw content storage with zero layout coupling. |
| **Contentful** | Hosted SaaS | GUI-first (Dashboard) | Large enterprise organizations requiring complex role governance, audit logs, and localization. | You are an indie hacker or startup with a tight budget, or you require code-based schema files. |
