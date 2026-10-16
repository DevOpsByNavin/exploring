## Node.js

Runtime that executes JS/TS on the server instead of the browser.

### Frameworks

1. Express.js

- Most popular, oldest, flexible, minimalist.
- Unopinionated (bare minimum, no enforced folder structure).
- Pros: massive ecosystem / middleware.
- Cons: unstructured projects become "spaghetti code".
- Best for: simple APIs, prototyping.

2. NestJS

- Enterprise-grade, opinionated (Angular-style DI, decorators, modules).
- Pros: scales across teams by forcing clean structure.
- Cons: boilerplate, overkill for simple projects.
- Best for: complex microservices / teams.

> Uses **Express.js** under the hood by default, or **Fastify** for better throughput.

3. Fastify

- Low-overhead, schema-based validation (JSON Schema → very fast payload checks) optimized for max RPS.
- Pros: fast, mature since 2016.
- Cons: smaller middleware ecosystem than Express.

4. Hono

- Ultra-light, runs everywhere (Node.js, Cloudflare Workers, Vercel functions, Bun, Deno) because it avoids Node-only APIs.
- Pros: tiny + fast on edge.
- Cons: younger ecosystem.
- Best for: serverless / edge.

Chooser: Express = prototype, Fastify = raw RPS on Node, Nest = team microservices, Hono = edge/serverless.
