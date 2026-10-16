## ORM

Instead of writing raw SQL, you use your programming language to query the DB — the ORM bridges backend code and the database.

### Prisma

- Most popular ORM in the JS/TS ecosystem.

**Working**

- Define the DB in Prisma Schema Language (PSL) in `schema.prisma`.
- Run `prisma migrate dev` — diffs schema vs DB, writes a SQL migration, applies it, then generates the type-safe TS client.
- Use the client directly in code:

```ts
// Instead of raw SQL:
const users = await db.query('SELECT * FROM users WHERE age > 18')

// Prisma:
const users = await prisma.user.findMany({ where: { age: { gt: 18 } } })
```

**Schema example**

```prisma
// schema.prisma

generator client {
  provider = "prisma-client-js"
}

datasource db {
  provider = "postgresql"   // or mysql, sqlite, etc.
  url      = env("DATABASE_URL")
}

model User {
  id    Int     @id @default(autoincrement())
  name  String
  age   Int?
}
```

Changing `schema.prisma` + `migrate dev` auto-generates the SQL to update the real DB structure.

Tradeoff: productive, heavyweight; historically painful on edge (engine binary) — check current engine status before using on Workers.

## Drizzle

- Lightweight, fast, growing TS ORM. Pure TS = edge-friendly (no engine binary).

**Working**

- Define schema directly in **TS**, write SQL-like but type-safe queries:

```ts
// Instead of raw SQL:
const users = await db.query('SELECT * FROM users WHERE age > 18')

// Drizzle:
const users = await db
  .select()
  .from(users)
  .where(gt(users.age, 18))
```

**Schema example**

```ts
import { pgTable, serial, text, integer } from 'drizzle-orm/pg-core'

export const users = pgTable('users', {
  id: serial('id').primaryKey(),
  name: text('name').notNull(),
  age: integer('age'),
})
```

Flow mirrors Prisma: edit `schema.ts` → `drizzle-kit generate` (SQL) → `drizzle-kit migrate`.

Pick Prisma for team velocity + migrations UX, Drizzle for edge / SQL control / tiny bundles.
