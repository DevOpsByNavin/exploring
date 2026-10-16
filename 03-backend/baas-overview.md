- Traditional way: You rent a server → install database → write auth system → write API endpoints → handle security → deploy → maintain it.
- BaaS: You sign up → create a project → get a URL + API key → start reading/writing data and authenticating users from your frontend.

## Features:

- Storage/DB
- Authentication
- Edge function

## What to choose

| Platform | Database | Best for | Self-hostable? | Pricing style | Notes |
| --- | --- | --- | --- | --- | --- |
| Supabase | PostgreSQL | Most web apps & SaaS | Yes | Free + $25/mo Pro | Current favorite for new projects. |
| Firebase | Firestore (NoSQL) | Mobile apps, offline-first | No | Pay-as-you-go | Best mobile SDKs + push notifications |
| Appwrite | Document / SQL (MariaDB) | Open-source + self-host preference | Yes (easy) | Free + $25/mo | Very complete self-hosted option with edge functions|
| PocketBase | SQLite | Tiny apps, MVPs, internal tools | Yes (single binary) | Free (you host it) | Extremely simple — single file, SQLite + auth + realtime + admin UI.|
