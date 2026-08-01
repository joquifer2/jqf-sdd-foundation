# Agentes metodológicos para Codex

Este directorio permite seleccionar en Codex los agentes metodológicos SDD de `jqf-sdd-foundation`.

## Jerarquía de fuentes

- `.github/agents/*.agent.md` contiene las definiciones canónicas de los roles.
- `.codex/agents/*.toml` adapta esas definiciones para Codex.
- `AGENTS.md` define el routing general del repositorio.
- `.github/instructions/sdd.instructions.md` define la fase y autorización vigentes.
- `docs/tasks.md` y los gates aplicables determinan el checkpoint de ejecución vigente.

Los archivos TOML no deben convertirse en una segunda fuente de verdad.

## Agentes disponibles

| Adaptador | Definición canónica | Modo de modificación |
|---|---|---|
| `legacy-to-sdd.toml` | `.github/agents/legacy-to-sdd.agent.md` | Según la solicitud autorizada |
| `specification.toml` | `.github/agents/specification.agent.md` | Según la solicitud autorizada |
| `reviewer.toml` | `.github/agents/reviewer.agent.md` | Solo lectura |
| `documentation.toml` | `.github/agents/documentation.agent.md` | Según la solicitud autorizada |
| `architect.toml` | `.github/agents/architect.agent.md` | Según la solicitud autorizada |
| `implementation.toml` | `.github/agents/implementation.agent.md` | Escritura en el workspace |
| `qa-gate.toml` | `.github/agents/qa-gate.agent.md` | Solo lectura |
| `tasks-planner.toml` | `.github/agents/tasks-planner.agent.md` | Según la solicitud autorizada |

## Agentes planeados

`GitHub Workflow Agent` figura en el catálogo metodológico general, pero todavía no tiene definición canónica en `.github/agents/`.

No debe crearse un adaptador TOML para ese agente hasta que exista su archivo `.github/agents/github-workflow.agent.md`.

## Límites específicos de la Foundation

- SDD gobierna los artefactos, las fases, la autorización, las tareas y los gates.
- La Foundation define metodología, gobernanza, agentes, templates y artefactos base reutilizables.
- Los repositorios derivados pueden instanciar artefactos reales de proyecto cuando exista instrucción explícita.
- GitHub es la ubicación canónica de los artefactos técnicos SDD de este repositorio.
- Ningún agente puede introducir runtime, integraciones, workflows ejecutables o automatizaciones productivas antes de la fase y autorización correspondientes.

## Uso de SDD Mode

Los adaptadores TOML no declaran modos ni crean variantes por modo.

Cada adaptador debe cargar `.github/instructions/sdd.instructions.md`, `docs/context_refs.md` y la definicion canonica del agente correspondiente para aplicar el `SDD Mode` vigente.

Si el modo no esta declarado, el agente debe tratar el trabajo como `Undeclared` y aplicar baseline conservador equivalente a `SDD Full` hasta que exista declaracion aprobada.
