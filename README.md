<p align="center">
  <img src="assets/hero.svg?v=2" alt="Kit VibeCoding Pro — las herramientas, los prompts y el método para programar con agentes de IA." width="100%" />
</p>

<p align="center">
  <b>Español</b> &nbsp;·&nbsp; <a href="README.en.md">English</a>
</p>

<p align="center">
  <a href="#-empieza-aquí"><b>Empieza aquí</b></a> &nbsp;·&nbsp;
  <a href="#-cómo-funciona"><b>Cómo funciona</b></a> &nbsp;·&nbsp;
  <a href="#-herramientas"><b>Herramientas</b></a> &nbsp;·&nbsp;
  <a href="#-prompts"><b>Prompts</b></a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Claude_Code-listo-ff4fa3?style=flat-square&labelColor=000000" alt="Claude Code listo" />
  <img src="https://img.shields.io/badge/Node-LTS-a1a1a6?style=flat-square&labelColor=000000" alt="Node LTS" />
  <img src="https://img.shields.io/badge/idioma-español-a1a1a6?style=flat-square&labelColor=000000" alt="Idioma español" />
  <img src="https://img.shields.io/badge/licencia-MIT-a1a1a6?style=flat-square&labelColor=000000" alt="Licencia MIT" />
  <a href="https://github.com/ivanvera7/kit-vibecoding-pro/stargazers"><img src="https://img.shields.io/github/stars/ivanvera7/kit-vibecoding-pro?style=flat-square&logo=github&label=estrellas&color=ff4fa3&labelColor=000000" alt="Estrellas en GitHub" /></a>
</p>

<p align="center"><sub>⭐ Si el kit te resulta útil, dale una estrella arriba a la derecha.</sub></p>

<br />

> **Tú describes el objetivo. El agente prepara, construye y lo demuestra.**
> Este kit reúne en un solo sitio las herramientas, los prompts y el método. El código vive en tu proyecto; aquí está la receta.

<br />

## ◇ Empieza aquí

| | Tu situación | Qué hacer | Frecuencia |
|:-:|---|---|---|
| **01** | Ordenador nuevo o sin configurar | Pega [`prompts/01-preparar-maquina.md`](prompts/01-preparar-maquina.md) | Una vez por ordenador |
| **02** | Tengo una idea | Pega [`prompts/02-proyecto-nuevo.md`](prompts/02-proyecto-nuevo.md) en una carpeta vacía | Una vez por proyecto |
| **03** | Ya tengo un proyecto | Pega [`prompts/03-proyecto-existente.md`](prompts/03-proyecto-existente.md) en su raíz | Una vez, y repítelo para actualizar |

```text
┌──────────────────────────┐      ┌──────────────────────────┐      ┌──────────────────────────┐
│  01 · MÁQUINA            │      │  02/03 · PROYECTO        │      │  DÍA A DÍA               │
│  herramientas globales   │ ───▶ │  AGENTS.md · CLAUDE.md   │ ───▶ │  "añade login"           │
│  plugins · hooks · MCP   │      │  scripts · tests · docs  │      │  "arregla este bug"      │
│  ── una vez ──           │      │  ── una vez ──           │      │  ── sin prompts extra ── │
└──────────────────────────┘      └──────────────────────────┘      └──────────────────────────┘
```

<br />

## ◇ Cómo funciona

<p align="center">
  <img src="assets/flow.svg?v=2" alt="El método en seis pasos: entender, diseñar, planificar, implementar, verificar y revisar." width="100%" />
</p>

Hay **dos capas**, y cada una se configura una sola vez.

<table>
<tr>
<td width="50%" valign="top">

### 🌐 Capa global
**Vive en tu ordenador. Se aplica en todos los proyectos.**

- Plugins de Claude Code: Superpowers, Ponytail, Caveman y Context7
- Hook de RTK sobre cada comando de terminal
- Skill de Graphify
- Node LTS con fnm y utilidades de terminal

*Se instala con el prompt 01.*

</td>
<td width="50%" valign="top">

### 📁 Capa de proyecto
**Vive en el repositorio. Se queda con el código.**

- `PRODUCT.md`: qué se construye y para quién
- `AGENTS.md` y `CLAUDE.md`: comandos y reglas para el agente
- `pnpm check`: lint, tipos y tests en un solo comando
- `docs/`: arquitectura y decisiones

*Se crea con el prompt 02 o el 03.*

</td>
</tr>
</table>

Después, cada sesión nueva de Claude lee `CLAUDE.md` y retoma el contexto. **Solo pides lo que quieres**; el método se aplica solo.

<br />

## ◇ Herramientas

<p align="center">
  <img src="assets/tools.svg?v=2" alt="Las ocho herramientas del kit." width="100%" />
</p>

| Herramienta | Para qué sirve | Origen |
|---|---|---|
| ✦ **Superpowers** | Brainstorming, planes, depuración y verificación | [`obra/superpowers`](https://github.com/obra/superpowers) |
| ◆ **Ponytail** | Reutilizar antes de construir; el cambio mínimo completo | [`DietrichGebert/ponytail`](https://github.com/DietrichGebert/ponytail) |
| ◐ **Caveman** | Respuestas compactas, menos tokens | [`JuliusBrussee/caveman`](https://github.com/JuliusBrussee/caveman) |
| ◎ **Context7** | Documentación actual de cada librería (MCP) | [`upstash/context7`](https://github.com/upstash/context7) |
| ⚡ **RTK** | Filtra la salida de la terminal antes de que llegue al agente | [`rtk-ai/rtk`](https://github.com/rtk-ai/rtk) |
| ⬡ **Graphify** | Grafo consultable del código | [`Graphify-Labs/graphify`](https://github.com/Graphify-Labs/graphify) |
| ⬢ **fnm** | La versión de Node correcta en cada proyecto | [`Schniz/fnm`](https://github.com/Schniz/fnm) |
| ⌘ **rg · fd · jq · gh · uv** | Buscar, procesar JSON, GitHub y Python | Homebrew |

→ Instalación y comprobación de cada una en [`docs/herramientas.md`](docs/herramientas.md).

<br />

## ◇ Prompts

Cada prompt es un bloque que se pega entero en Claude Code. **No es un comando de terminal.**

<details>
<summary><b>01 · Preparar la máquina</b> &nbsp;—&nbsp; instala y valida toda la capa global</summary>
<br />

Hace inventario y backup, instala lo que falta, reutiliza lo que ya funciona, configura los plugins y el hook, y valida todo en una sesión nueva. Solo te pide intervenir para contraseñas o inicios de sesión.

→ [`prompts/01-preparar-maquina.md`](prompts/01-preparar-maquina.md)
</details>

<details>
<summary><b>02 · Proyecto nuevo</b> &nbsp;—&nbsp; de la idea a una base Next.js verificada</summary>
<br />

Brainstorming → `PRODUCT.md` → Next.js + TypeScript + Tailwind + Drizzle/PostgreSQL + Zod + Vitest → contexto para agentes → `pnpm check` en verde → primer commit → primera tarea del MVP.

→ [`prompts/02-proyecto-nuevo.md`](prompts/02-proyecto-nuevo.md)
</details>

<details>
<summary><b>03 · Proyecto existente</b> &nbsp;—&nbsp; aplica el kit sin cambiar tu stack</summary>
<br />

Conocer → decidir contigo → configurar → mejorar en pasos pequeños → comparar el antes y el después. Si lo repites, actualiza en lugar de duplicar.

→ [`prompts/03-proyecto-existente.md`](prompts/03-proyecto-existente.md)
</details>

O úsalos directamente desde la URL:

```text
Lee https://raw.githubusercontent.com/ivanvera7/kit-vibecoding-pro/main/prompts/02-proyecto-nuevo.md y ejecútalo en este directorio.
Proyecto: [tu idea]
```

<br />

## ◇ Principios

<table>
<tr>
<td align="center" width="25%"><h3>🧭</h3><b>Pensar primero</b><br /><sub>Ningún código sin entender el objetivo</sub></td>
<td align="center" width="25%"><h3>✂️</h3><b>Lo mínimo completo</b><br /><sub>Reutilizar antes de construir</sub></td>
<td align="center" width="25%"><h3>🔬</h3><b>Evidencia, no promesas</b><br /><sub>Algo está hecho cuando se ha comprobado</sub></td>
<td align="center" width="25%"><h3>🧠</h3><b>Contexto que persiste</b><br /><sub>El siguiente agente continúa donde lo dejó el anterior</sub></td>
</tr>
</table>

<br />

## ◇ Estructura

```text
kit-vibecoding-pro/
├── README.md                     ← estás aquí
├── prompts/
│   ├── 01-preparar-maquina.md    capa global
│   ├── 02-proyecto-nuevo.md      idea → proyecto
│   ├── 03-proyecto-existente.md  proyecto → proyecto con el kit
│   └── en/                       los mismos prompts en inglés
├── docs/
│   └── herramientas.md           ficha de cada herramienta
└── assets/                       gráficos del README
```

<br />

---

<p align="center">
  <a href="https://github.com/ivanvera7/kit-vibecoding-pro">
    <img src="https://img.shields.io/github/stars/ivanvera7/kit-vibecoding-pro?style=for-the-badge&logo=github&label=Dale%20una%20estrella&color=ff4fa3&labelColor=000000" alt="Dale una estrella en GitHub" />
  </a>
</p>

<p align="center">
  <b>¿Te ha servido el kit?</b> Dale una ⭐ al repositorio: ayuda a que más gente lo encuentre.
</p>

<p align="center">
  <sub>Hecho por <a href="https://github.com/ivanvera7">Ivan Vera</a> · Licencia MIT</sub>
</p>
