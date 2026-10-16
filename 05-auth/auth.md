## Basics

Covers:

- Password hashing
- Session management (cookies, JWTs, tokens)
- Security (XSS, CSRF, timing attacks, `httpOnly` / `SameSite` / `Secure` cookies)
- Social logins (Google, GitHub, Apple OAuth + PKCE)
- Password resets, email verification, MFA

### Passwords

- Hashing: Argon2id, bcrypt (or scrypt).
- Salting: per-password random string, so identical passwords get different hashes.
- Peppering: app-wide secret outside the DB added to the password before hashing.

### Session management

Persist identity across requests.

#### Stateful sessions

- DB/Redis + opaque cookie.
- Instant revocation (delete the row).
- Cost: a DB/Redis lookup per request.

#### Stateless sessions (JWT)

- JWT = Header + Payload + Signature (header/payload are base64url-encoded, not encrypted).
- Server verifies the signature — no DB lookup.
- Hard to revoke; standard fix is short-lived access token + rotating refresh token stored server-side.

## Approaches

Two main approaches:

1. **Auth provider** — SaaS handling the whole flow via SDK.
2. **Self-hosted libraries** — tools for sessions/OAuth/adapters; you own storage and security.

### Auth providers

#### Clerk

- Ready-made customizable UI components.
- Generous free tier (~50k MAU).
- Con: vendor lock-in.

#### Auth0 (Okta)

- Battle-tested OG, enterprise standard (organizations, RBAC, logs).
- Con: complex, pricier at scale.

#### Supabase Auth

- Built into the Supabase BaaS (Postgres + RLS + storage). Cheapest path if already on Supabase.

### DIY / self-hosted

#### Auth.js (NextAuth.js v5)

- OAuth providers, email/password, session management, DB adapters.
- Most Next.js examples target it; still Next-centric. More work than a provider.

#### Better Auth (current pick for framework-agnostic)

- TypeScript-first, adapters for Prisma/Drizzle, social + email/password + MFA, works on Node and edge.
- Replaces Lucia (deprecated/archived by its author in 2025).
