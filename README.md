# HR AI Assistant (Internal — Prototype)

Internal HR chat assistant with mocked AI streaming responses.
Bilingual (Arabic/English), RTL-aware, intranet-only — no real backend.

See [`docs/context.md`](./docs/context.md) for full scope, MVP definition,
and what's intentionally cut for this iteration.

## Requirements
- Node version pinned in `.nvmrc` (use `nvm use` if you have nvm installed)
- No environment variables needed — everything is mocked, no real API keys

## Getting started

\`\`\`bash
npm install
npm run dev
\`\`\`

Open http://localhost:3000

## Running tests

\`\`\`bash
npm test          # unit tests (Jest + Testing Library)
npm run test:watch
npx playwright test   # end-to-end tests
\`\`\`

## Linting & formatting

\`\`\`bash
npx eslint . --max-warnings=0
\`\`\`

Formatting and lint-fixing run automatically on commit via Husky + lint-staged.
Accessibility rules (jsx-a11y) are enforced as lint errors, not warnings.

## Project structure

\`\`\`
src/
  app/            → Next.js routes only, no business logic
  features/       → auth, chat, dashboard — each self-contained
  shared/         → locale (RTL/i18n context), ui (generic components)
  lib/mock-api/   → mocked auth + streaming endpoints
docs/adr/         → architectural decisions, with reasoning
\`\`\`

## Key architectural decisions

Full reasoning lives in `docs/adr/`. Summary:
- **0001** — Next.js App Router (needed for real streaming support)
- **0002** — Lightweight custom locale context, not a full i18n library
- **0003** — React Query for chat history/session, Zustand for live
  streaming buffer + UI state
- **0004** — Tailwind with logical properties (`ms-`/`me-`) for RTL,
  not physical (`ml-`/`mr-`)
- **0005** — AI streaming is mocked via a real `ReadableStream` Route
  Handler, not faked client-side — this matters if you're extending
  the chat feature

## Before opening a PR

See `.github/pull_request_template.md` — it encodes the project's
Definition of Done (RTL check, a11y, cross-browser, tests, CI).