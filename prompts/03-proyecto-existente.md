# 03 · Proyecto existente

> **Cuándo:** ya tienes código y quieres aplicarle el kit, o actualizar un proyecto que ya lo tenía.
> **Dónde:** abre Claude Code en la raíz del proyecto y pega el bloque.

```markdown
Aplica el Kit VibeCoding Pro a este proyecto sin cambiar su stack.

## 1. Conocer
Inspecciona el producto, el stack, las dependencias, los scripts, los tests, la CI y los archivos de instrucciones (`AGENTS.md`, `CLAUDE.md`, `README.md`). No modifiques nada todavía.

## 2. Decidir
Haz brainstorming conmigo. Preséntame:
- Qué falta o está desactualizado en el contexto para agentes
- Mejoras de calidad (lint, tipos, tests, scripts), ordenadas por impacto
- Riesgos y lo que NO vas a tocar
Espera mi aprobación antes de seguir.

## 3. Configurar
- Crea o actualiza `AGENTS.md` (comandos, estructura, convenciones) y `CLAUDE.md` con `@AGENTS.md`
- Añade un script `check` que ejecute lint, tipos y tests con las herramientas que ya usa el proyecto
- Añade `.graphifyignore` y, si el proyecto es grande, genera el grafo con `/graphify .`
- Conserva la base de datos, el gestor de paquetes, la versión de Node y los contratos existentes

## 4. Mejorar
Aplica las mejoras aprobadas en pasos pequeños; verifica cada uno antes de pasar al siguiente.

## 5. Demostrar
Compara el antes y el después ejecutando `check`. Lista lo que quedó pendiente y por qué.

Si este prompt ya se ejecutó antes en este proyecto, actualiza en lugar de duplicar.
```
