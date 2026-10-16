## Python

Use when you interact with LLMs, process data, or need heavy math.

1. **FastAPI**
   - Modern standard for Python APIs.
   - Uses Python type hints for validation + auto-generated docs.
   - For microservices.

2. Django
   - Monolith (ORM, admin panel, auth included), older yet powerful.
   - For data / content-heavy apps.

3. Flask
   - Minimal. Mostly replaced by FastAPI for new APIs.

## Go

- Lightweight, fast, simple. Compiles to a single tiny binary; built for high concurrency.
- Frameworks are thin routers over stdlib: **Gin**, **Echo**, **Fiber**, **Chi**.

> Use for real-time chat servers, high-throughput infra, single-binary deploys.

## Rust

- Fastest, safest, lightest — steep learning curve.

> Use where every millisecond is expensive (edge, proxies, infra). **Axum** is dominant alongside **Actix-web**.

## PHP (Laravel)

- Still relevant because of **Laravel**: auth, queues, websockets, ORM out of the box.

> Use for solo-founder CRUD / content-heavy sites with cheap shared hosting.

## Elixir

- Functional language (2011) running on the Erlang VM (1986), famous for fault-tolerant concurrency.
- **Phoenix** + **LiveView**: write only backend code; the server keeps per-user state and pushes tiny HTML diffs over WebSockets — SPA feel with no JS framework.

> Use for chat apps, live collaboration, multiplayer, anything with instant concurrent push. Cost: stateful connections (sticky sessions / clustering).

## Corporate giants (Java & C#)

- Java: **Spring Boot** powers much of global finance.
- C#: **ASP.NET Core** is fast and modern, strongest inside the Microsoft ecosystem (enterprise, games).
