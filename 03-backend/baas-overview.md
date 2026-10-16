- Traditional: rent a server → install DB → write auth → write APIs → handle security → deploy → maintain.
- BaaS: sign up → create project → get URL + API key → read/write data and auth users from the frontend.

## Features

- Database / storage
- Authentication + authorization (RLS / security rules)
- Edge functions, realtime subscriptions, cron

## What to choose

| Platform | Database | Best for | Self-hostable? | Pricing style | Notes |
| --- | --- | --- | --- | --- | --- |
| Supabase | PostgreSQL (relational) | Most web apps & SaaS | Yes | Free + $25/mo Pro | Current favorite. Postgres + RLS. |
| Firebase | Firestore (NoSQL) | Mobile, offline-first | No | Pay-as-you-go | Best mobile SDKs + push. Rules, not RLS. |
| Appwrite | Document / MariaDB | Open-source + self-host preference | Yes (easy) | Free + $25/mo | Complete self-hosted option with functions. |
| PocketBase | SQLite | Tiny apps, MVPs, internal tools | Yes (single binary) | Free (you host) | Single file: SQLite + auth + realtime + admin UI. |

Note: Convex intentionally skipped (real-time document DB, not evaluated here).
