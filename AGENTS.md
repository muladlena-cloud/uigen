# AGENTS

## Purpose
This file helps AI coding agents understand the repository quickly so they can make safe, relevant changes.

## Primary conventions
- Next.js 15 App Router + React 19 + TypeScript.
- Tailwind CSS v4 for styling.
- Prisma with SQLite for persistence.
- Anthropic Claude integration for AI chat; the app falls back to a mock provider when `ANTHROPIC_API_KEY` is not configured.
- Generated Prisma client files live under `src/generated/prisma`; do not edit these directly.
- The app uses a virtual file system in the UI, so generated components are often stored in application state rather than disk files.

## Setup and commands
- `npm run setup` — install dependencies, generate Prisma client, run migrations.
- `npm run dev` — start the development server.
- `npm run build` — build the app.
- `npm run lint` — run Next.js lint checks.
- `npm test` — run Vitest tests.
- `npm run db:reset` — reset Prisma database.

> Important: do not run `npm audit fix`. Dependencies are pinned to specific versions that work together.

## Key project areas
- `README.md` — setup instructions, environment behavior, and project purpose.
- `package.json` — dependency versions and scripts.
- `next.config.ts` — Turbopack root pinning and dev indicators.
- `prisma/schema.prisma` — database schema and migrations.
- `src/lib/prisma.ts` — Prisma client instantiation.
- `src/app` — app routes, layouts, and API route for chat.
- `src/components/auth` — authentication UI.
- `src/components/chat` — chat interface, message input, Markdown rendering.
- `src/components/editor` — code editor and virtual file tree.
- `src/components/preview/PreviewFrame.tsx` — live preview UI.
- `src/actions` — server-side actions for project persistence.
- `src/hooks/use-auth.ts` — auth helper hook.
- `src/lib/file-system.ts` — virtual file system logic.

## AI agent guidance
- Prefer working within the existing App Router structure.
- Keep changes aligned with the chat/editor/preview flow.
- Avoid editing generated client code under `src/generated/prisma`.
- Use `README.md` for setup and runtime behavior rather than inferring from package versions alone.
- For any database-related change, update `prisma/schema.prisma` and use Prisma migrations.

## Testing conventions
- Unit and component tests use Vitest.
- Test files are typically located alongside components in `__tests__` directories.
