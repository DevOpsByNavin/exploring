## Basics

It includes:

- Password hashing
- Session management (cookies, JWTs, tokens)
- Security (protecting against XSS, CSRF, timing attacks)
- Social logins (Google, GitHub, Apple OAuth flows)
- Password resets, email verification, MFA

### Passwords

- Hashing: Argon2id, bcrypt
- Salting: Add random string to password; ensure two same password have different hash
- Peppering: A secret key outside db is also added to password.

### Session management

Persist identity of user across multiple request

#### Stateful Sessions

- DB/Redis + cookie
- Instant revocation
- Every request needs a db record to compare

#### Stateless Sessions

- Uses JWT (Header + Payload + Signature)
- Header and Payload are encoded
- The server only verify the signature based on Header + Payload, so it doesn't need to use db.
- As a result it's hard to revoke; often paired with refresh token + short lived access token.

## Approaches

It includes two main approach

1. [Auth Provider](#Auth-Provider)  
  SasS platform that handle entire auth flow through their SDK

2. [Open source Libraries](#)  
  Gives you tools to build auth, but you handle the implementation, database storage, and security yourself.

### Auth Provider

#### Clerk

- Ready to use, customizable UI component
- Generous free tier (50K MRU)
- But vendor lock-in

#### Autho0

- Battle tested, the OG
- Enterprise standard, so complex and pricier

#### Supabase Auth

- Integrated with their overall BaaS suite

OpenSource DIY


### DIY

#### Auth.js (NextAuth.js)

- Framework agnostic and full control
- Comes with OAuth provider, session management, email/pass auth, db adapter, etc
- More work

#### Lucia

- Newer, Minimalist, lightweight, unopinionated, flexible
- provides basic to build yourself
- doesn't give oauth provider by itself
- session management, user validation, db adapter
