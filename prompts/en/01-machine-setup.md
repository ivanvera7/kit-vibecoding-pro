# 01 · Machine setup

> **When:** once per computer, or whenever you want to update everything.
> **Where:** open Claude Code in any folder and paste the whole block below.

```markdown
Set up this computer for coding with AI agents using Kit VibeCoding Pro. Do the work; don't give me a tutorial.

## Rules
- Before changing anything, take an inventory: OS, shell, PATH, package manager, runtimes, and Claude Code plugins, MCP servers and hooks.
- Back up `~/.claude/settings.json`, `~/.claude.json` and the shell files to `~/.vibe-setup/backup-<date>/`.
- Reuse whatever already works. Never install the same tool with two different package managers.
- Preserve projects, credentials, hooks and custom configuration.
- Only ask me to step in for passwords, logins or costs. Never ask for secrets in the chat.
- It must be repeatable: a second run verifies and updates without duplicating anything.

## System base (macOS: Homebrew; Linux: the distro's package manager)
- git, gh, ripgrep (`rg`), fd, jq, uv
- fnm with Node LTS as the default and automatic per-project switching (`--use-on-cd`)
- pnpm through its official mechanism

## Claude Code extensions (user scope)
- **Superpowers**: `claude plugin install superpowers@claude-plugins-official`
- **Ponytail**: marketplace `DietrichGebert/ponytail`, plugin `ponytail@ponytail`, `full` mode
- **Caveman**: marketplace `JuliusBrussee/caveman`, plugin `caveman@caveman`
- **Context7**: marketplace `upstash/context7`, plugin `context7@context7-marketplace`; then tell me to log in with `/mcp`
- **RTK**: `brew install rtk-ai/tap/rtk`, `rtk init --global`, and register `rtk hook claude` as a `PreToolUse` hook (matcher `Bash`) in `~/.claude/settings.json` without removing existing hooks
- **Graphify**: `uv tool install graphifyy` (two "y"s) and `graphify install --platform claude`

## Validation (in a fresh zsh session)
- Version and path of every tool
- `claude plugin list` shows all four plugins
- `claude mcp list` shows Context7 connected
- The RTK hook rewrites `git status` into `rtk git status`

## Deliverable
A table with every component (status, version, method), the files changed, the backup path and anything that still depends on me.
```
