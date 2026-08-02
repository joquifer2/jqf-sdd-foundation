# Reference Map - Repository Physical Normalization

## Estado

| Campo | Valor |
| --- | --- |
| Fase | Development |
| Estado | Post-execution controlled map for review |
| Desarrollo | AUTHORIZED for first SDD Modes wave |
| Alcance | Primera ola SDD Modes ejecutada; referencias activas actualizadas en expediente RPN e indices globales; referencias historicas preservadas |

## Proposito

Este mapa identifica el tratamiento aplicado a las referencias principales tras ejecutar la primera ola de normalizacion fisica de SDD Modes.

No pretende reescribir todas las referencias historicas de capacidades cerradas. Las rutas legacy se preservan mediante stubs cuando corresponden a artefactos movidos.

## Rutas bajo control tras ejecucion

| ID | Ruta legacy | Tratamiento legacy | Ruta canonica vigente | Riesgo residual |
| --- | --- | --- | --- | --- |
| RM-SM-001 | `docs/project_brief.md` | Stub de routing | `docs/capabilities/sdd-modes/project_brief.md` | Bajo |
| RM-SM-002 | `docs/context_refs.md` | Stub de routing | `docs/capabilities/sdd-modes/context_refs.md` | Bajo |
| RM-SM-003 | `docs/tasks.md` | Stub de routing | `docs/capabilities/sdd-modes/tasks.md` | Bajo |
| RM-SM-004 | `docs/sdd_readiness_assessment.md` | Stub de routing | `docs/capabilities/sdd-modes/sdd_readiness_assessment.md` | Bajo |
| RM-SM-005 | `specs/spec-001-sdd-modes.md` | Stub de routing | `specs/capabilities/sdd-modes/spec-001-sdd-modes.md` | Bajo |
| RM-SM-006 | `specs/spec-001-sdd-modes.architecture.md` | Legacy canonical retained | `specs/spec-001-sdd-modes.architecture.md` | Medio; movement deferred |

## Superficies de referencia detectadas y tratamiento

| Superficie | Evidencia encontrada | Tratamiento aplicado |
| --- | --- | --- |
| Baseline SDD Modes moved artifacts | Los cinco artefactos movidos existen en rutas canonicas. | Rutas legacy sustituidas por stubs de routing. |
| Architecture SDD Modes | `specs/spec-001-sdd-modes.architecture.md` tiene referencias numerosas y condicion QA. | Ruta legacy retenida; no se mueve ni renombra en esta ola. |
| Indices globales | `docs/capabilities/index.md` y `specs/capabilities/index.md`. | Actualizados a rutas canonicas y nota de compatibilidad legacy. |
| Repository Physical Normalization | SPEC, ARCH, tasks, readiness, context refs y paquete GEP. | Actualizados hacia estado Development first wave / pending review. |
| Capacidades cerradas | Project Consolidation and Closure, Foundation Derivation and Project Initialization y Consolidation Agent contienen referencias historicas a rutas legacy. | No se reescriben en esta ola; stubs preservan navegacion. |
| Agentes e instrucciones | `.github/agents`, `.codex/agents` e instrucciones contienen referencias genericas a rutas raiz SDD. | No se tratan automaticamente como SDD Modes; stubs preservan compatibilidad. |
| Plantillas y glosario | Referencias genericas a `docs/context_refs.md` y `docs/tasks.md`. | No se modifican; stubs preservan compatibilidad para rutas legacy. |

## Clasificacion de accion por referencia

| Tipo de referencia | Accion aplicada | Condicion residual |
| --- | --- | --- |
| Referencia activa en indices globales | Actualizada a ruta canonica | Reviewer/QA post-Development deben confirmar. |
| Referencia activa en RPN | Actualizada o documentada como ejecutada/diferida | Reviewer/QA post-Development deben confirmar. |
| Referencia historica a expediente cerrado | Mantenida | Stub legacy preserva navegacion. |
| Referencia de instruccion generica del harness | Mantenida | No se asume que sea referencia concreta a SDD Modes. |
| Referencia a Architecture SDD Modes | Mantenida en ruta legacy | Decision futura requerida solo si se desea mover/renombrar. |

## Validacion post-ejecucion requerida

Reviewer Agent debe validar:

- que las rutas canonicas existen;
- que las rutas legacy movidas son stubs;
- que `specs/spec-001-sdd-modes.architecture.md` permanece disponible;
- que indices globales enrutan correctamente;
- que no hay scripts, workflows, tools ni automatizaciones;
- que no se reescribio contenido normativo de SDD Modes salvo stubs de compatibilidad en rutas legacy.

QA Gate Agent debe validar despues si la primera ola puede cerrarse con o sin condiciones.