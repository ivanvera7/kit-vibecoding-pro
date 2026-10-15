# 02 · New project

> **When:** you have an idea and an empty folder.
> **Where:** open Claude Code in that folder, paste the block and fill in the last line.

```markdown
Create a new project in this directory following the Kit VibeCoding Pro method.

## 1. Understand (before writing any code)
Brainstorm with me: problem, audience, main flows, MVP, out of scope and acceptance criteria. Ask me one question at a time and wait for my answer. Summarize the result in `PRODUCT.md`.

## 2. Technical base
Check the current docs for each piece with Context7 before configuring it.
- Official Next.js (`create-next-app`): App Router, strict TypeScript, Tailwind CSS and ESLint
- pnpm as the package manager and `.node-version` with the current Node LTS
- If there is persistent data: Drizzle ORM + PostgreSQL. If not needed, explain why and skip them.
- Zod to validate at the boundaries, Pino for server logs and Vitest for tests
- Canonical scripts in `package.json`: `dev`, `build`, `lint`, `typecheck`, `test`, `check` (the last one runs everything)

## 3. Context for agents
- `AGENTS.md`: commands, structure, conventions and short rules
- `CLAUDE.md`: a single `@AGENTS.md` line plus anything Claude-specific
- `README.md`: how to install and run
- `docs/`: architecture, decisions (ADRs) and MVP status
- `.graphifyignore` excluding `node_modules`, `.next` and generated files

## 4. Verify
Run `pnpm check` and start `pnpm dev`. Show me real evidence; don't assume it works.
Initialize git and make a first commit.

## 5. Next step
Finish by proposing the first MVP task with its plan.

Project: [name, problem, audience, main flows and constraints]
```

**Example last line:**
`Project: Booking app for barbershops. Clients book from their phone; the barber sees their day and blocks slots. English UI, MVP focused on bookings.`
