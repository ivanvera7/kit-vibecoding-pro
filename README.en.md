<p align="center">
  <img src="assets/hero-en.svg?v=2" alt="Kit VibeCoding Pro — the tools, the prompts and the method for coding with AI agents." width="100%" />
</p>

<p align="center">
  <a href="README.md">Español</a> &nbsp;·&nbsp; <b>English</b>
</p>

<p align="center">
  <a href="#-start-here"><b>Start here</b></a> &nbsp;·&nbsp;
  <a href="#-how-it-works"><b>How it works</b></a> &nbsp;·&nbsp;
  <a href="#-tools"><b>Tools</b></a> &nbsp;·&nbsp;
  <a href="#-prompts"><b>Prompts</b></a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Claude_Code-ready-ff4fa3?style=flat-square&labelColor=000000" alt="Claude Code ready" />
  <img src="https://img.shields.io/badge/Node-LTS-a1a1a6?style=flat-square&labelColor=000000" alt="Node LTS" />
  <img src="https://img.shields.io/badge/license-MIT-a1a1a6?style=flat-square&labelColor=000000" alt="MIT license" />
  <a href="https://github.com/ivanvera7/kit-vibecoding-pro/stargazers"><img src="https://img.shields.io/github/stars/ivanvera7/kit-vibecoding-pro?style=flat-square&logo=github&label=stars&color=ff4fa3&labelColor=000000" alt="GitHub stars" /></a>
</p>

<p align="center"><sub>⭐ If the kit is useful to you, star it at the top right.</sub></p>

<br />

> **You describe the goal. The agent sets up, builds and proves it.**
> This kit brings the tools, the prompts and the method together in one place. The code lives in your project; the recipe lives here.

<br />

## ◇ Start here

| | Your situation | What to do | How often |
|:-:|---|---|---|
| **01** | New or unconfigured computer | Paste [`prompts/en/01-machine-setup.md`](prompts/en/01-machine-setup.md) | Once per computer |
| **02** | I have an idea | Paste [`prompts/en/02-new-project.md`](prompts/en/02-new-project.md) in an empty folder | Once per project |
| **03** | I already have a project | Paste [`prompts/en/03-existing-project.md`](prompts/en/03-existing-project.md) at its root | Once, then re-run to update |

```text
┌──────────────────────────┐      ┌──────────────────────────┐      ┌──────────────────────────┐
│  01 · MACHINE            │      │  02/03 · PROJECT         │      │  DAY TO DAY              │
│  global tools            │ ───▶ │  AGENTS.md · CLAUDE.md   │ ───▶ │  "add login"             │
│  plugins · hooks · MCP   │      │  scripts · tests · docs  │      │  "fix this bug"          │
│  ── once ──              │      │  ── once ──              │      │  ── no extra prompts ──  │
└──────────────────────────┘      └──────────────────────────┘      └──────────────────────────┘
```

<br />

## ◇ How it works

<p align="center">
  <img src="assets/flow-en.svg?v=2" alt="The six-step method: understand, design, plan, implement, verify and review." width="100%" />
</p>

There are **two layers**, and each is set up only once.

<table>
<tr>
<td width="50%" valign="top">

### 🌐 Global layer
**Lives on your computer. Applies to every project.**

- Claude Code plugins: Superpowers, Ponytail, Caveman and Context7
- RTK hook on every terminal command
- Graphify skill
- Node LTS via fnm, plus terminal utilities

*Installed with prompt 01.*

</td>
<td width="50%" valign="top">

### 📁 Project layer
**Lives in the repo. Stays with the code.**

- `PRODUCT.md`: what is being built and for whom
- `AGENTS.md` and `CLAUDE.md`: commands and rules for the agent
- `pnpm check`: lint, types and tests in one command
- `docs/`: architecture and decisions

*Created with prompt 02 or 03.*

</td>
</tr>
</table>

After that, every new Claude session reads `CLAUDE.md` and picks up the context. **Just ask for what you want**; the method applies itself.

<br />

## ◇ Tools

<p align="center">
  <img src="assets/tools-en.svg?v=2" alt="The eight tools in the kit." width="100%" />
</p>

| Tool | What it does | Source |
|---|---|---|
| ✦ **Superpowers** | Brainstorming, plans, debugging and verification | [`obra/superpowers`](https://github.com/obra/superpowers) |
| ◆ **Ponytail** | Reuse before you build; the minimal complete change | [`DietrichGebert/ponytail`](https://github.com/DietrichGebert/ponytail) |
| ◐ **Caveman** | Compact answers, fewer tokens | [`JuliusBrussee/caveman`](https://github.com/JuliusBrussee/caveman) |
| ◎ **Context7** | Current docs for every library (MCP) | [`upstash/context7`](https://github.com/upstash/context7) |
| ⚡ **RTK** | Filters terminal output before it reaches the agent | [`rtk-ai/rtk`](https://github.com/rtk-ai/rtk) |
| ⬡ **Graphify** | Queryable knowledge graph of your code | [`Graphify-Labs/graphify`](https://github.com/Graphify-Labs/graphify) |
| ⬢ **fnm** | The right Node version in every project | [`Schniz/fnm`](https://github.com/Schniz/fnm) |
| ⌘ **rg · fd · jq · gh · uv** | Search, JSON, GitHub and Python tooling | Homebrew |

<details>
<summary><b>Quick install commands</b></summary>
<br />

```bash
# System
brew install ripgrep fd jq gh uv fnm rtk-ai/tap/rtk

# Claude Code plugins
claude plugin install superpowers@claude-plugins-official
claude plugin marketplace add DietrichGebert/ponytail   && claude plugin install ponytail@ponytail
claude plugin marketplace add JuliusBrussee/caveman     && claude plugin install caveman@caveman
claude plugin marketplace add upstash/context7          && claude plugin install context7@context7-marketplace

# RTK hook + Graphify
rtk init --global
uv tool install graphifyy && graphify install --platform claude
```

> `rtk init --global` doesn't edit `settings.json` in non-interactive mode. Make sure this `PreToolUse` hook exists:
> `{"matcher":"Bash","hooks":[{"type":"command","command":"rtk hook claude"}]}`
</details>

<br />

## ◇ Prompts

Each prompt is a block you paste whole into Claude Code. **It is not a terminal command.**

<details>
<summary><b>01 · Machine setup</b> &nbsp;—&nbsp; installs and validates the whole global layer</summary>
<br />

Takes an inventory and a backup, installs what's missing, reuses what already works, configures plugins and hooks, and validates everything in a fresh session. It only asks you to step in for passwords or logins.

→ [`prompts/en/01-machine-setup.md`](prompts/en/01-machine-setup.md)
</details>

<details>
<summary><b>02 · New project</b> &nbsp;—&nbsp; from idea to a verified Next.js base</summary>
<br />

Brainstorming → `PRODUCT.md` → Next.js + TypeScript + Tailwind + Drizzle/PostgreSQL + Zod + Vitest → agent context → green `pnpm check` → first commit → first MVP task.

→ [`prompts/en/02-new-project.md`](prompts/en/02-new-project.md)
</details>

<details>
<summary><b>03 · Existing project</b> &nbsp;—&nbsp; applies the kit without changing your stack</summary>
<br />

Discover → decide with you → configure → improve in small steps → compare before and after. Re-running it updates instead of duplicating.

→ [`prompts/en/03-existing-project.md`](prompts/en/03-existing-project.md)
</details>

Or use them straight from the URL:

```text
Read https://raw.githubusercontent.com/ivanvera7/kit-vibecoding-pro/main/prompts/en/02-new-project.md and run it in this directory.
Project: [your idea]
```

<br />

## ◇ Principles

<table>
<tr>
<td align="center" width="25%"><h3>🧭</h3><b>Think first</b><br /><sub>No code without understanding the goal</sub></td>
<td align="center" width="25%"><h3>✂️</h3><b>Minimal and complete</b><br /><sub>Reuse before you build</sub></td>
<td align="center" width="25%"><h3>🔬</h3><b>Evidence, not promises</b><br /><sub>Done means verified</sub></td>
<td align="center" width="25%"><h3>🧠</h3><b>Context that persists</b><br /><sub>The next agent picks up where the last one left off</sub></td>
</tr>
</table>

<br />

---

<p align="center">
  <a href="https://github.com/ivanvera7/kit-vibecoding-pro">
    <img src="https://img.shields.io/github/stars/ivanvera7/kit-vibecoding-pro?style=for-the-badge&logo=github&label=Star%20it&color=ff4fa3&labelColor=000000" alt="Star it on GitHub" />
  </a>
</p>

<p align="center">
  <b>Did the kit help you?</b> Give the repo a ⭐ — it helps more people find it.
</p>

<p align="center">
  <sub>Made by <a href="https://github.com/ivanvera7">Ivan Vera</a> · MIT License</sub>
</p>
