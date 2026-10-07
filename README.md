# Local-Supplier-Matcher

Replit export (`replit.com/@serenebuilding/Local-Supplier-Matcher`) containing the standard pnpm monorepo scaffold — Express API server skeleton, OpenAPI/Zod/Drizzle libs — plus a Replit design-preview sandbox artifact. The supplier-matching app itself is not implemented in this repo.

## Features

- **API server scaffold** (`artifacts/api-server`) — Express 5 + TypeScript service skeleton with routes, middleware, and `app.ts`/`index.ts` entry points.
- **Shared libs** (`lib/`) — `api-spec` (OpenAPI), `api-client-react`, `api-zod` (Zod schemas), `db` (Drizzle ORM + PostgreSQL).
- **Mockup sandbox** (`artifacts/mockup-sandbox`) — a Replit "Canvas" design artifact: a Vite + React component-preview server (serves previews at `/__mockup`) used for iterating on UI components, not the supplier matcher itself.

## Tech stack

Node.js 24, TypeScript 5.9, pnpm workspaces, React 18, Vite, Express 5, PostgreSQL + Drizzle ORM, Zod, Orval (OpenAPI codegen), esbuild.

## Getting started

From `replit.md` (project-name template left unfilled):

- `pnpm --filter @workspace/api-server run dev` — run the API server (port 5000)
- `pnpm run typecheck` — full typecheck across all packages
- `pnpm run build` — typecheck + build all packages
- `pnpm --filter @workspace/api-spec run codegen` — regenerate API hooks and Zod schemas from the OpenAPI spec
- `pnpm --filter @workspace/db run push` — push DB schema changes (dev only)
- Required env: `DATABASE_URL` — Postgres connection string

## Project structure

```
.
├── artifacts/
│   ├── api-server/       # Express 5 API skeleton
│   └── mockup-sandbox/   # "Canvas" design-preview sandbox artifact
├── lib/
│   ├── api-spec/         # OpenAPI spec (codegen source of truth)
│   ├── api-client-react/ # generated React API client
│   ├── api-zod/          # generated Zod schemas
│   └── db/               # Drizzle ORM schema
└── scripts/              # workspace helpers
```

## Status

**Stub / scaffold only.** The workspace scaffolding is real, but nothing in the repo implements supplier matching — the app exists only as the Replit project name. The GitHub description points to https://replit.com/@serenebuilding/Local-Supplier-Matcher.
