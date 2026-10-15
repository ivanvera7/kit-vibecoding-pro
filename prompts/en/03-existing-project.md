# 03 · Existing project

> **When:** you already have code and want to apply the kit, or update a project that already has it.
> **Where:** open Claude Code at the project root and paste the block.

```markdown
Apply Kit VibeCoding Pro to this project without changing its stack.

## 1. Discover
Inspect the product, stack, dependencies, scripts, tests, CI and instruction files (`AGENTS.md`, `CLAUDE.md`, `README.md`). Don't change anything yet.

## 2. Decide
Brainstorm with me. Present:
- What is missing or outdated in the agent context
- Quality improvements (lint, types, tests, scripts), ranked by impact
- Risks and what you will NOT touch
Wait for my approval before continuing.

## 3. Configure
- Create or update `AGENTS.md` (commands, structure, conventions) and `CLAUDE.md` with `@AGENTS.md`
- Add a `check` script that runs lint, types and tests with the tools the project already uses
- Add `.graphifyignore` and, if the project is large, build the graph with `/graphify .`
- Preserve the database, package manager, Node version and existing contracts

## 4. Improve
Apply the approved improvements in small steps; verify each one before moving on.

## 5. Prove
Compare before and after by running `check`. List what is still pending and why.

If this prompt has already been run on this project, update instead of duplicating.
```
