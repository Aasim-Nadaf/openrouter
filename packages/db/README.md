# db

Shared Prisma package for the workspace. Add it to any workspace app with:

```bash
bun add db --cwd apps/<app-name>
```

Then import the singleton Prisma client from the package export:

```ts
import { prisma } from "db/client";

const users = await prisma.user.findMany();
```

Keep Prisma imports in server-side code only: API handlers, server actions,
route handlers, or backend services. Do not import `db/client` into a browser
component, because it requires `DATABASE_URL` and a database connection.

Each app that uses this package needs a `DATABASE_URL` environment variable.

To install dependencies:

```bash
bun install
```

To run:

```bash
bun run index.ts
```

This project was created using `bun init` in bun v1.3.14. [Bun](https://bun.com) is a fast all-in-one JavaScript runtime.
