## Heroku

- No free tier anymore. Massive add-on marketplace (Postgres, Redis, logging).
- Use when: legacy docs / add-ons matter. Otherwise Railway/Render are cheaper.

## Railway

- Heroku-like DX (services, containers, cron, DBs). Free started as trial credits — check current plan, not ongoing free.
- Use when: quick Node + Postgres prototype you outgrow locally.

## Render

- Web services, background workers, static sites, managed Postgres/Redis. Docker support.
- Use when: simple persistent full-stack app with managed DB.

## Koyeb

- Global containers with autoscaling + load balancing.
- Use when: multi-region containers without Kubernetes.

## Fly.io

- Runs containers close to users (per-region volumes, anycast). Great for Elixir/Phoenix, Go, SQLite (LiteFS).
- Use when: global stateful containers / WebSockets.

## Coolify

- Self-hosted PaaS (Dokku/Cloudron-style control plane) on your own VPS.
- Use when: you want Heroku UX on hardware you own. You handle backups/uptime.

| Platform | Category | What it really is |
| --- | --- | --- |
| Heroku | App PaaS | Managed dynos + add-ons |
| Railway | General-purpose PaaS | Services, containers, jobs, DBs |
| Render | General-purpose PaaS | Web services, workers, static, DBs |
| Koyeb | Container PaaS | Global autoscaled containers |
| Fly.io | Global container platform | Containers + volumes near users |
| Coolify | Self-hosted PaaS | Heroku-like UX on your VPS |
