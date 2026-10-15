# 01 · Preparar la máquina

> **Cuándo:** una vez por ordenador, o cuando quieras actualizarlo todo.
> **Dónde:** abre Claude Code en cualquier carpeta y pega el bloque de abajo completo.

```markdown
Prepara este ordenador para programar con agentes de IA usando el Kit VibeCoding Pro. Ejecuta el trabajo; no me des un tutorial.

## Reglas
- Antes de tocar nada, haz un inventario: sistema, shell, PATH, gestor de paquetes, runtimes, plugins, MCPs y hooks de Claude Code.
- Haz backup de `~/.claude/settings.json`, `~/.claude.json` y de los archivos del shell en `~/.vibe-setup/backup-<fecha>/`.
- Reutiliza lo que ya funcione. No instales la misma herramienta con dos gestores distintos.
- Conserva los proyectos, credenciales, hooks y configuraciones personalizadas.
- Pídeme intervención solo para contraseñas, inicios de sesión o costes. Nunca me pidas secretos en el chat.
- Debe poder repetirse: una segunda ejecución verifica y actualiza, sin duplicar.

## Base del sistema (macOS: Homebrew; Linux: gestor de la distro)
- git, gh, ripgrep (`rg`), fd, jq, uv
- fnm con Node LTS como predeterminado y cambio automático por proyecto (`--use-on-cd`)
- pnpm por el mecanismo oficial

## Extensiones de Claude Code (alcance de usuario)
- **Superpowers**: `claude plugin install superpowers@claude-plugins-official`
- **Ponytail**: marketplace `DietrichGebert/ponytail`, plugin `ponytail@ponytail`, modo `full`
- **Caveman**: marketplace `JuliusBrussee/caveman`, plugin `caveman@caveman`
- **Context7**: marketplace `upstash/context7`, plugin `context7@context7-marketplace`; después indícame que haga login con `/mcp`
- **RTK**: `brew install rtk-ai/tap/rtk`, `rtk init --global` y registra `rtk hook claude` como hook `PreToolUse` (matcher `Bash`) en `~/.claude/settings.json` sin borrar hooks existentes
- **Graphify**: `uv tool install graphifyy` (con dos «y») y `graphify install --platform claude`

## Validación (en una sesión nueva de zsh)
- Versión y ruta de cada herramienta
- `claude plugin list` muestra los cuatro plugins
- `claude mcp list` muestra Context7 conectado
- El hook de RTK reescribe `git status` como `rtk git status`

## Entrega
Una tabla con cada componente (estado, versión, método), los archivos modificados, la ruta del backup y lo que dependa de mí.
```
