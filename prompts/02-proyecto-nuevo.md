# 02 · Proyecto nuevo

> **Cuándo:** tienes una idea y una carpeta vacía.
> **Dónde:** abre Claude Code en esa carpeta, pega el bloque y rellena la última línea.

```markdown
Crea un proyecto nuevo en este directorio siguiendo el método del Kit VibeCoding Pro.

## 1. Entender (antes de escribir código)
Haz brainstorming conmigo: problema, público, flujos principales, MVP, fuera de alcance y criterios de aceptación. Hazme las preguntas de una en una y espera mi respuesta. Resume el resultado en `PRODUCT.md`.

## 2. Base técnica
Consulta con Context7 la documentación actual de cada pieza antes de configurarla.
- Next.js oficial (`create-next-app`): App Router, TypeScript estricto, Tailwind CSS y ESLint
- pnpm como gestor y `.node-version` con el Node LTS actual
- Si hay datos persistentes: Drizzle ORM + PostgreSQL. Si no hacen falta, justifícalo y omítelos.
- Zod para validar en las fronteras, Pino para logs del servidor y Vitest para tests
- Scripts canónicos en `package.json`: `dev`, `build`, `lint`, `typecheck`, `test`, `check` (este último ejecuta todo)

## 3. Contexto para agentes
- `AGENTS.md`: comandos, estructura, convenciones y reglas cortas
- `CLAUDE.md`: una línea `@AGENTS.md` y lo específico de Claude
- `README.md`: cómo instalar y ejecutar
- `docs/`: arquitectura, decisiones (ADR) y estado del MVP
- `.graphifyignore` para excluir `node_modules`, `.next` y archivos generados

## 4. Verificar
Ejecuta `pnpm check` y arranca `pnpm dev`. Muéstrame la evidencia real, no supongas que funciona.
Inicializa git y haz un primer commit.

## 5. Siguiente paso
Termina proponiendo la primera tarea del MVP con su plan.

Proyecto: [nombre, problema, público, flujos principales y restricciones]
```

**Ejemplo de última línea:**
`Proyecto: Agenda para barberías. Los clientes reservan cita desde el móvil; el barbero ve su día y bloquea huecos. Interfaz en español, MVP centrado en reservas.`
