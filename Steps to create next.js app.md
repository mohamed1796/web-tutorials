
**to create the project run** 

```bash
bunx create-next-app@latest [place-project-name] --app --javascript --react-compiler --tailwind --biome --no-src-dir --import-alias "@/*"
```

**Create DB using Prisma**
```bash
bun add -d prisma
bun add @prisma/client
```


**Initialize Prisma**
```
bunx prisma init
```

**Configure database**
```
DATABASE_URL="file:./db/dev.db"
```

# Define schema

`prisma/schema.prisma`

```
generator client {
  provider = "prisma-client-js"
}

datasource db {
  provider = "sqlite" 
  url      = env("DATABASE_URL")
}

// Example
model User {
  id    Int     @id @default(autoincrement())
  name  String
  email String  @unique
}
```

**Run migration**
```bash
bunx prisma migrate dev --name init
```

**Generate client manually (if needed)**
```bash
bunx prisma generate
```



Source:
https://chatgpt.com/c/69f8c8cb-04e0-83eb-9c0b-eb684c9765ab