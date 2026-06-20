# SDD Readiness Assessment Template

## Propósito

Este documento evalúa si un proyecto existente está suficientemente preparado para continuar su evolución bajo metodología SDD.

Su objetivo es determinar si el proyecto puede avanzar hacia nuevas specifications, arquitectura, planificación o implementación con suficiente contexto, trazabilidad y control.

Este documento no aprueba por sí mismo el paso a Development.

Este documento no sustituye la revisión humana.

Este documento debe ser revisado por el Reviewer Agent o QA Gate Agent antes de utilizarse como base para nuevas fases SDD.

---

# Información General

| Campo | Valor |
|---|---|
| Project Name | |
| Repository | |
| Assessment Type | Legacy to SDD / Brownfield to SDD / Other |
| Project Type | Greenfield / Brownfield / Legacy |
| Repository Type | Foundation / Derived Project / Unknown |
| Last Updated | |
| Assessor | |
| Reviewer | |

---

# Resumen Ejecutivo

Describir brevemente:

- estado general del proyecto;
- nivel de preparación para SDD;
- principales huecos;
- principales riesgos;
- siguiente paso recomendado.

---

# Estado General

Seleccionar uno:

| Estado | Descripción |
|---|---|
| Ready | El proyecto puede continuar bajo SDD sin bloqueos críticos. |
| Partially Ready | El proyecto puede avanzar, pero existen huecos o riesgos que deben resolverse. |
| Not Ready | El proyecto no debería avanzar hasta resolver huecos críticos. |

Estado seleccionado:

---

# Artefactos SDD Existentes

| Artefacto | Existe | Path | Estado | Observaciones |
|---|---|---|---|---|
| context_refs.md | Yes / No / Partial | | Current / Outdated / Unknown | |
| system_overview.md | Yes / No / Partial | | Current / Outdated / Unknown | |
| retrospective_spec.md | Yes / No / Partial | | Current / Outdated / Unknown | |
| architecture_as_is.md | Yes / No / Partial | | Current / Outdated / Unknown | |
| data_lineage.md | Yes / No / Not Applicable / Partial | | Current / Outdated / Unknown | |
| contracts.md | Yes / No / Not Applicable / Partial | | Current / Outdated / Unknown | |
| docs/tasks.md | Yes / No / Partial | | Current / Outdated / Unknown | |
| ADRs / decisions | Yes / No / Partial | | Current / Outdated / Unknown | |

---

# Artefactos SDD Faltantes

| Artefacto | Obligatorio | Motivo | Impacto |
|---|---|---|---|
| | Yes / No / Conditional | | |

Criterios orientativos:

- `context_refs.md` es obligatorio si el proyecto necesita gobernanza de fuentes de contexto.
- `system_overview.md` es obligatorio para proyectos legacy o brownfield.
- `retrospective_spec.md` es obligatorio si el comportamiento actual no está documentado.
- `architecture_as_is.md` es obligatorio si existen componentes técnicos relevantes.
- `data_lineage.md` es obligatorio si el proyecto tiene pipelines, BigQuery, dbt, BI, APIs de datos o activaciones.
- `contracts.md` es obligatorio unicamente cuando existan contratos transversales o interfaces estables cuya comprension sea necesaria para la evolucion segura del sistema. Si los contratos estan suficientemente documentados en `architecture_as_is.md`, `data_lineage.md` o `retrospective_spec.md`, no es obligatorio separarlos en un artefacto independiente.
- `sdd_readiness_assessment.md` es obligatorio para declarar readiness del proyecto.

---

# Evaluación por Dimensión

## Contexto

| Criterio | Estado | Evidencia | Observaciones |
|---|---|---|---|
| Existe contexto suficiente del proyecto | Pass / Partial / Fail | | |
| Existe mapa de fuentes de contexto | Pass / Partial / Fail | | |
| Las fuentes principales están identificadas | Pass / Partial / Fail | | |

---

## Funcional

| Criterio | Estado | Evidencia | Observaciones |
|---|---|---|---|
| El propósito actual está documentado | Pass / Partial / Fail | | |
| Las capacidades actuales están documentadas | Pass / Partial / Fail | | |
| Las reglas de negocio actuales están documentadas o marcadas como UNKNOWN | Pass / Partial / Fail | | |
| Los inputs y outputs funcionales están identificados | Pass / Partial / Fail | | |

---

## Arquitectura

| Criterio | Estado | Evidencia | Observaciones |
|---|---|---|---|
| Los componentes principales están identificados | Pass / Partial / Fail | | |
| Las dependencias principales están identificadas | Pass / Partial / Fail | | |
| Los flujos principales están descritos | Pass / Partial / Fail | | |
| Los riesgos arquitectónicos están identificados | Pass / Partial / Fail | | |

---

## Datos

| Criterio | Estado | Evidencia | Observaciones |
|---|---|---|---|
| Las fuentes de datos están identificadas | Pass / Partial / Fail / N/A | | |
| Las capas de datos están identificadas | Pass / Partial / Fail / N/A | | |
| El lineage mínimo está documentado | Pass / Partial / Fail / N/A | | |
| Los consumidores de datos están identificados | Pass / Partial / Fail / N/A | | |
| Los riesgos de trazabilidad están documentados | Pass / Partial / Fail / N/A | | |

---

## Integraciones

| Criterio | Estado | Evidencia | Observaciones |
|---|---|---|---|
| Los sistemas externos están identificados | Pass / Partial / Fail / N/A | | |
| La dirección de integración está identificada | Pass / Partial / Fail / N/A | | |
| Los contratos relevantes están documentados o marcados como Missing | Pass / Partial / Fail / N/A | | |
| Los riesgos de integración están identificados | Pass / Partial / Fail / N/A | | |

---

## Operación / Runtime

| Criterio | Estado | Evidencia | Observaciones |
|---|---|---|---|
| Los runtimes principales están identificados | Pass / Partial / Fail / N/A | | |
| Los triggers están identificados | Pass / Partial / Fail / N/A | | |
| Las dependencias operativas están identificadas | Pass / Partial / Fail / N/A | | |
| Los riesgos operativos están identificados | Pass / Partial / Fail / N/A | | |

---

# Riesgos Críticos

| Riesgo | Severidad | Bloquea avance | Evidencia |
|---|---|---|---|
| | Critical / Important / Minor | Yes / No | |

---

# Unknowns Críticos

| Unknown | Impacto | Validación requerida | Bloquea avance |
|---|---|---|---|
| | | | Yes / No |

---

# Decisión de Readiness

Seleccionar una:

## Ready

El proyecto puede continuar bajo SDD.

Condiciones:

- no hay riesgos críticos bloqueantes;
- los artefactos mínimos existen o están suficientemente completos;
- las incógnitas restantes no bloquean la siguiente fase;
- el siguiente agente puede trabajar sin redescubrir el sistema desde cero.

## Partially Ready

El proyecto puede avanzar parcialmente, pero deben resolverse huecos concretos.

Condiciones:

- existen artefactos mínimos parciales;
- hay riesgos importantes, pero no necesariamente bloqueantes;
- algunas incógnitas requieren validación;
- el siguiente agente puede avanzar con restricciones.

## Not Ready

El proyecto no debería avanzar todavía.

Condiciones:

- faltan artefactos críticos;
- existen riesgos críticos bloqueantes;
- las incógnitas impiden definir una specification fiable;
- el siguiente agente tendría que redescubrir el sistema desde cero.

Decisión:

---

# Acciones Mínimas Requeridas

| Acción | Tipo | Prioridad | Responsable |
|---|---|---|---|
| | Documentation / Specification / Architecture / Review / Validation | High / Medium / Low | |

---

# Siguiente Agente Recomendado

Seleccionar uno:

- Specification Agent
- Architect Agent
- Documentation Agent
- Reviewer Agent
- QA Gate Agent
- Tasks Planner Agent
- Implementation Agent

Agente recomendado:

Motivo:

---

# Artefactos Relacionados

- context_refs.md
- system_overview.md
- retrospective_spec.md
- architecture_as_is.md
- data_lineage.md
- contracts.md
- docs/tasks.md
- decisions / ADRs

---

# Definition of Done

Este assessment está completo cuando permite responder:

1. ¿Qué artefactos SDD existen?
2. ¿Qué artefactos SDD faltan?
3. ¿Qué dimensiones están suficientemente documentadas?
4. ¿Qué riesgos bloquean la evolución?
5. ¿Qué unknowns requieren validación?
6. ¿El proyecto está Ready, Partially Ready o Not Ready?
7. ¿Qué acciones mínimas deben completarse?
8. ¿Qué agente debe intervenir después?

---

# Notas

Este documento evalúa preparación, no implementación.

La decisión final debe ser revisada por una persona responsable o por el QA Gate Agent.
