# Herramientas del kit

Ficha rápida de cada pieza: qué hace, cómo se instala y cómo saber si funciona.

---

### ✦ Superpowers — el método
Skills que obligan al agente a pensar antes de programar: brainstorming, planes, depuración sistemática, TDD y verificación antes de dar algo por terminado.

```bash
claude plugin install superpowers@claude-plugins-official
```
**Funciona si:** al pedir algo nuevo, el agente empieza preguntando y proponiendo un diseño.

---

### ◆ Ponytail — el alcance justo
Antes de escribir, el agente sigue una escalera fija de decisiones: ¿ya existe? ¿se puede reutilizar? Solo entonces construye, y lo hace con el cambio más pequeño que sea completo.

```bash
claude plugin marketplace add DietrichGebert/ponytail
claude plugin install ponytail@ponytail
```
**Modo por defecto:** `full`. Para cambiarlo, usa `PONYTAIL_DEFAULT_MODE` o `~/.config/ponytail/config.json`.

---

### ◐ Caveman — conversación compacta
Respuestas cortas y directas, con menos tokens. El código, la documentación y los commits se escriben con normalidad.

```bash
claude plugin marketplace add JuliusBrussee/caveman
claude plugin install caveman@caveman
```
**Funciona si:** al abrir una sesión aparece «Loading caveman mode…». Si quieres una explicación larga, pídela.

---

### ◎ Context7 — documentación al día
Servidor MCP que da al agente la documentación actual de cada librería y versión. Así no se inventa APIs que ya cambiaron.

```bash
claude plugin marketplace add upstash/context7
claude plugin install context7@context7-marketplace
# después, dentro de Claude: /mcp → context7 → iniciar sesión
```
**Funciona si:** `claude mcp list` muestra `context7 … ✔ Connected`.

---

### ⚡ RTK — terminal sin ruido
Rust Token Killer. Un hook reescribe los comandos (`git status` → `rtk git status`) y filtra la salida repetitiva antes de que llegue al agente.

```bash
brew install rtk-ai/tap/rtk
rtk init --global
```
> El instalador no toca `settings.json` en modo no interactivo. Comprueba que existe este hook `PreToolUse`:
> `{"matcher":"Bash","hooks":[{"type":"command","command":"rtk hook claude"}]}`

**Funciona si:** `rtk gain` muestra los tokens ahorrados.

---

### ⬡ Graphify — mapa del código
Convierte un proyecto en un grafo de conocimiento consultable: módulos clave, relaciones y comunidades.

```bash
uv tool install graphifyy        # con dos «y»
graphify install --platform claude
```
**Uso:** dentro de un proyecto, `/graphify .`

---

### ⬢ fnm + Node LTS — el runtime correcto
Gestor de versiones de Node. Cambia de versión solo al entrar en un proyecto con `.node-version` o `.nvmrc`.

```bash
brew install fnm
fnm install --lts && fnm default lts-latest
echo 'eval "$(fnm env --use-on-cd --version-file-strategy=recursive --shell zsh)"' >> ~/.zshrc
```

---

### ⌘ Utilidades — rg · fd · jq · gh · uv
Búsqueda rápida (`rg`, `fd`), JSON (`jq`), GitHub desde la terminal (`gh`) y herramientas de Python (`uv`).

```bash
brew install ripgrep fd jq gh uv
```
