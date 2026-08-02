# Canonical Route Registry - Repository Physical Normalization

## Estado

| Campo | Valor |
| --- | --- |
| Fase | Development |
| Estado | Closed - DEV-RPN-010 |
| Development | AUTHORIZED for first SDD Modes wave |
| Movimiento fisico | Executed for DEV-RPN-001..DEV-RPN-005 and DEV-RPN-010 |

## Proposito

Este registro define las rutas canonicas vigentes tras la primera ola controlada de normalizacion fisica sobre SDD Modes.

La ejecucion conserva stubs de compatibilidad en rutas legacy y no modifica contenido normativo de SDD Modes.

## Principios de ruta canonica

1. El baseline metodologico canonico debe vivir bajo `specs/capabilities/<capability-id>/` cuando pertenezca a una capacidad concreta.
2. Los expedientes documentales de capacidad deben vivir bajo `docs/capabilities/<capability-id>/`.
3. La documentacion transversal debe permanecer en rutas transversales como `README.md`, `AGENTS.md`, `.github/instructions/`, `.github/agents/`, `.codex/agents/`, `docs/templates/`, `specs/templates/` y `docs/glosario_terminos.md`.
4. Las evidencias de consolidacion o validacion deben permanecer bajo el expediente de la capacidad que las produjo, salvo decision humana explicita de derivar un resumen en otro expediente.
5. Ninguna ruta legacy se elimina en la primera ejecucion; la compatibilidad se preserva mediante stubs de routing.

## Registro canonico - SDD Modes piloto

| ID | Ruta legacy antes de ejecucion | Ruta canonica vigente | Clasificacion | Accion ejecutada | Condicion aplicada | Estado actual |
| --- | --- | --- | --- | --- | --- | --- |
| CRR-SM-001 | `docs/project_brief.md` | `docs/capabilities/sdd-modes/project_brief.md` | Expediente de capacidad / alcance inicial | Move + legacy stub | Development autorizado; Reference Map final ejecutado; compatibilidad por stub | Executed |
| CRR-SM-002 | `docs/context_refs.md` | `docs/capabilities/sdd-modes/context_refs.md` | Expediente de capacidad / indice de contexto | Move + legacy stub | Development autorizado; Reference Map final ejecutado; compatibilidad por stub | Executed |
| CRR-SM-003 | `docs/tasks.md` | `docs/capabilities/sdd-modes/tasks.md` | Expediente historico / decision log | Move + legacy stub | Development autorizado; Reference Map final ejecutado; compatibilidad por stub | Executed |
| CRR-SM-004 | `docs/sdd_readiness_assessment.md` | `docs/capabilities/sdd-modes/sdd_readiness_assessment.md` | Evidencia de readiness y gates | Move + legacy stub | Development autorizado; Reference Map final ejecutado; compatibilidad por stub | Executed |
| CRR-SM-005 | `specs/spec-001-sdd-modes.md` | `specs/capabilities/sdd-modes/spec-001-sdd-modes.md` | Baseline canonico de Specification | Move + legacy stub | Development autorizado; Reference Map final ejecutado; compatibilidad por stub | Executed |
| CRR-SM-006 | `specs/spec-001-sdd-modes.architecture.md` | `specs/capabilities/sdd-modes/arch-001-sdd-modes.md` | Baseline canonico de Architecture | Move + rename + legacy stub | DEV-RPN-010 autorizado por T-035 tras Reviewer T-033 y QA T-034 | Executed |
| CRR-SM-007 | N/A | `docs/capabilities/sdd-modes/closure_handover.md` | Resumen derivado de cierre | Not executed | No requerido para primera ola | Deferred |
| CRR-SM-008 | N/A | `docs/capabilities/sdd-modes/evidence_index.md` | Resumen derivado de evidencias | Not executed | No requerido para primera ola | Deferred |
| CRR-SM-009 | N/A | `docs/capabilities/sdd-modes/residual_debt.md` | Resumen derivado de deuda residual | Not executed | No requerido para primera ola | Deferred |

## Rutas que se mantienen transversales

| Ruta | Clasificacion | Regla |
| --- | --- | --- |
| `README.md` | Documentacion transversal del repositorio | Mantener; actualizar solo si review/QA post-ejecucion lo requiere. |
| `AGENTS.md` | Catalogo transversal de agentes metodologicos | Mantener; no convertir en expediente de capacidad. |
| `.github/instructions/sdd.instructions.md` | Instrucciones metodologicas transversales | Mantener; no mover bajo SDD Modes. |
| `.github/agents/*.agent.md` | Definiciones canonicas de agentes | Mantener; no duplicar como baseline de SDD Modes. |
| `.codex/agents/` | Adaptadores Codex | Mantener; no fuente canonica. |
| `docs/templates/` | Plantillas documentales | Mantener transversal. |
| `specs/templates/` | Plantillas de specification/architecture | Mantener transversal. |
| `docs/glosario_terminos.md` | Glosario transversal | Mantener transversal. |

## Criterio de salida post-ejecucion

Este registro queda listo para review post-Development cuando cada ruta afectada tenga ruta legacy, ruta canonica vigente, accion ejecutada o diferida, condicion aplicada y estado actual.

---

## Architecture Route Decision Execution - CRR-SM-006

| Campo | Valor |
| --- | --- |
| Artefacto | `specs/spec-001-sdd-modes.architecture.md` |
| Decision propuesta | Option A |
| Ruta canonica vigente | `specs/capabilities/sdd-modes/arch-001-sdd-modes.md` |
| Accion ejecutada | Move + rename + legacy stub |
| Estado | QA passed with minor conditions - T-038 |
| Evidencia | `docs/capabilities/repository-physical-normalization/governed-execution-preparation/sdd_modes_architecture_route_decision.md` |

La ruta canonica vigente es `specs/capabilities/sdd-modes/arch-001-sdd-modes.md`. La ruta legacy `specs/spec-001-sdd-modes.architecture.md` queda como stub no normativo de compatibilidad.