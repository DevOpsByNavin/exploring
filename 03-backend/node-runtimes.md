## Node.js

Runtime env that execute js/ts on the server side instead of client side.

### Frameworks

1. Express.js

- Most popular, oldest, flexible and minimalist
- Unopinionated (gives bare minimum to work with and doesn't force to org file in certain order)
- Pros: Massive ecosystem
- Cons: if not structured can turn onto "spaghetti code"
- Best for: Simple API, Prototyping

2. NestJS

- Enterprise grade, opinionated, highly strucutred framework
- Pros: Scalable cause it forces you to write clean, organized code
- Cons: Tons of boilerplate and overkill for a simple project
- Best for: complex microservices

> It uses **Expres.js** under the hood by default but can also use **Fastify** for better performance

3. Fastify

- low overhead framework optimized to maximize rps
- Pros: Fast (using schema-based validation i.e, validate incoming API payload within fraction)
- Cons: Growing ecosystem, Node.js centric

4. Hono

- Ultra-modern, lightweight, fast, minimalist.
- Pros: runs everywhere (Node.js, Cloudflare Worker, Vercel function, Bun, Deno) and blazingly fast.
- Cons: Growing ecosystem
- Best for: Serverless/Edge computing
