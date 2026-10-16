## ORM

- instead of writing raw sql query to interact with db
- you instead use programming language to carry out same task
- i.e, bridges backend with db

### Prisma

- most pouplar ORM
- Used in JS/TS ecosystem

**Working**

- define entire 'db' structure using Prisma Schema Language (PSL) in a `.prisma` file
- run `prisma generate`, to generate type-safe TS client
- you then use this client directly in code,

```ts
// Instead of writing raw SQL like this:
const users = await db.query('SELECT * FROM users WHERE age > 18')

// You write this with Prisma:
const users = await prisma.user.findMany({ where: { age: { gt: 18 } } })
```

**Schema Example**

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
````

It makes migration hassle free,  
Let's say you changed your `.prisma` schema, then it auto generates new SQL migration file to update actual db strucutre.


## Drizzle

- super lightweight and faster
- fast growing TS ORM, runs natively on edge env

**Working**

- define entire 'db' structure directly in **TS**
- you then write queries that look very close to SQL, but stay fully type-safe


```ts
// Instead of writing raw SQL like this:
const users = await db.query('SELECT * FROM users WHERE age > 18')

// You write this with Drizzle:
const users = await db
  .select()
  .from(users)
  .where(gt(users.age, 18))
```

**Schema Example**

```ts
import { pgTable, serial, text, integer } from 'drizzle-orm/pg-core'

export const users = pgTable('users', {
  id: serial('id').primaryKey(),
  name: text('name').notNull(),
  age: integer('age'),
})
```
