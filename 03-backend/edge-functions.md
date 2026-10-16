> It uses a combo of edge function and serverless db.

## Features:

- Compute and Storage are different things
- Compute can scale down to zero if not in use

## Serverless DB

1. PostgreSQL
  - Neon
  - Supabase (Database)
  - CockroachDB: enterprise level

2. Key-Value Pair
  - Upstash: Serverless Redis
  - DynamoDB

3. Edge-Native DB

> Primarily uses distributed **SQLite** across many regions

  - Turso (**libSQL**): instant data read
  - Cloudflare D1

## Edge Function

Simple function that are distributed across regions.

- Cloudflare Worker: Integrates with **D1**, **R2**, **KV**
- Vercel/Netlify function
- Deno Deploy
