# AGENTS.md

## Propósito

Este documento describe los agentes definidos dentro del proyecto.

Su función es proporcionar una visión centralizada de:

- agentes metodológicos heredados;
- agentes operativos propios;
- responsabilidades;
- estado de madurez;
- artefactos SDD relacionados;
- skills, gates y evaluaciones asociadas.

No sustituye a las specifications de cada agente.

No define lógica funcional completa.

No sustituye la Source of Truth del proyecto.

---

## Información general

### Proyecto

{{PROJECT_NAME}}

### Estado SDD actual

{{SDD_PHASE}}

Valores habituales:

- Proposed
- Specification
- Structure
- Development
- Validation
- Active
- Deprecated

### Última actualización

{{LAST_UPDATED}}

---

## Relación con la Foundation

Este proyecto deriva de:

jqf-sdd-foundation

Por tanto hereda:

- metodología SDD;
- SDD Harness;
- agentes metodológicos;
- reglas de gobernanza;
- precedencia documental;
- gates;
- skills metodológicas;
- convenciones de documentación.

---

## Agentes metodológicos heredados

Estos agentes forman parte de la Foundation y gobiernan el ciclo SDD del proyecto.

| Agente | Responsabilidad principal |
|---|---|
| Specification Agent | Crear y revisar specifications |
| Architect Agent | Diseñar estructura documental y arquitectura conceptual |
| Tasks Planner Agent | Transformar specifications en tareas trazables |
| Reviewer Agent | Revisar coherencia, alcance y calidad documental |
| Documentation Agent | Mantener documentación consistente y actualizada |
| QA Gate Agent | Validar readiness y cumplimiento de criterios de fase |
| Implementation Agent | Supervisar transición controlada hacia Development |
| GitHub Workflow Agent | Gestionar trazabilidad entre documentación y GitHub |

---

## Agentes operativos

Registrar aquí los agentes específicos del proyecto.

| ID | Nombre | Estado | Specification | Responsabilidad |
|---|---|---|---|---|
| AGENT-001 | {{AGENT_NAME}} | Draft | SPEC-001 | {{SHORT_DESCRIPTION}} |

---

## Estados permitidos

Los agentes pueden encontrarse en alguno de los siguientes estados:

- Draft
- Specification
- Structure
- Development
- Validation
- Active
- Deprecated

---

## Relación con Specifications

Todo agente operativo debe estar vinculado a una specification.

Ejemplo:

- SPEC-001 → reporting_agent
- SPEC-002 → forecasting_agent
- SPEC-003 → analytics_agent

No deben existir agentes operativos sin specification.

---

## Relación con Skills

Los agentes pueden utilizar skills reutilizables.

| Agente | Skill |
|---|---|
| {{AGENT_NAME}} | {{SKILL_NAME}} |

---

## Relación con Gates

Los agentes deben superar los gates definidos por el proyecto antes de avanzar de fase.

Los gates validan:

- alcance;
- trazabilidad;
- readiness;
- criterios de aceptación;
- calidad documental.

---

## Relación con Evals

Los agentes pueden disponer de evaluaciones específicas para validar:

- comportamiento esperado;
- calidad de salida;
- cumplimiento de requisitos;
- alineación con la specification.

| Agente | Eval |
|---|---|
| {{AGENT_NAME}} | {{EVAL_NAME}} |

---

## Source of Truth

La Source of Truth funcional del proyecto es:

{{SOURCE_OF_TRUTH}}

Todo agente debe respetar dicha fuente.

No debe duplicar lógica funcional.

No debe reinterpretar reglas de negocio.

---

## Principios de gobierno

Todo agente debe:

- tener specification;
- tener alcance definido;
- tener límites definidos;
- tener criterios de aceptación;
- respetar la Source of Truth;
- respetar la metodología SDD;
- mantener trazabilidad documental.

---

## Definition of Done

Un agente puede considerarse listo para Development cuando:

- existe specification aprobada;
- existe alcance definido;
- existen criterios de aceptación;
- existe trazabilidad documental;
- ha superado los gates correspondientes;
- cuenta con validación humana.

---

## Historial de cambios

| Fecha | Cambio |
|---|---|
| {{DATE}} | Creación inicial del catálogo de agentes |