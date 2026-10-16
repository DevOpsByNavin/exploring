The edge pattern = edge functions (compute) + serverless DBs (storage), scaled independently.

## Key idea

- Compute and storage are separate. Compute scales to zero instantly when idle.
- Gotcha: Workers cold-start in ms, but serverless Postgres (e.g. Neon) wakes in hundreds of ms. First request after idle pays the DB wake-up.

## Serverless DB

1. PostgreSQL
   - Neon (scale-to-zero, HTTP driver)
   - Supabase (database)
   - CockroachDB (enterprise)

2. Key-value
   - Upstash (serverless Redis)
   - DynamoDB

3. Edge-native (distributed SQLite, replicated per region)
   - Turso (**libSQL**): instant reads
   - Cloudflare D1

Rule: from edge, always use the **pooled** connection (Neon `-pooler` host / Hyperdrive). Edge runtimes can't hold direct Postgres connections.

## Edge functions

Small handlers replicated across regions (V8 isolates, not Node: no native modules, short timeouts, no persistent connections).

- Cloudflare Workers: integrate with **D1**, **R2**, **KV**
- Vercel Edge / Netlify Edge functions (isolate) vs Node serverless functions (full Node APIs, slower cold start)
- Deno Deploy
