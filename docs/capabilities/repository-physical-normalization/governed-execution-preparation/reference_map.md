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

---

## Full Reference Map - SDD Modes Architecture Route

Reference scan realizado sobre:

```text
specs/spec-001-sdd-modes.architecture.md
spec-001-sdd-modes.architecture.md
specs/capabilities/sdd-modes/arch-001-sdd-modes.md
arch-001-sdd-modes.md
```

Decision propuesta: `Option A`, mover a `specs/capabilities/sdd-modes/arch-001-sdd-modes.md` con stub legacy.

| Clase | Archivos detectados | Tratamiento futuro |
| --- | --- | --- |
| Active SDD Modes dossier | `docs/capabilities/sdd-modes/tasks.md`; `docs/capabilities/sdd-modes/context_refs.md`; `docs/capabilities/sdd-modes/sdd_readiness_assessment.md`; `specs/capabilities/sdd-modes/spec-001-sdd-modes.md` | Update to target path during authorized DEV-RPN-010. |
| Active global indexes | `docs/capabilities/index.md`; `specs/capabilities/index.md` | Update to target path during authorized DEV-RPN-010. |
| Active RPN package | RPN Project Brief, Context References, Readiness, Tasks, SPEC, ARCH, GEP artifacts | Update live routing references; preserve historical decision references where they describe prior state. |
| Closed capability references | Project Consolidation and Closure, Foundation Derivation and Project Initialization, Consolidation Agent | Keep as historical references; legacy stub preserves navigation. |
| Retrospective evidence | `docs/capabilities/consolidation-agent/validations/sdd-modes-retrospective/*` | Keep unchanged as evidence of prior physical state; legacy stub preserves navigation. |
| Legacy architecture artifact | `specs/spec-001-sdd-modes.architecture.md` | Future move target; content remains normatively unchanged except route metadata if explicitly authorized. |

Blocking assessment:

- No blocking active reference has been found that requires permanent exception B.
- Historical references are compatible with Option A if the legacy route becomes a non-normative stub.
- Rollback is viable because DEV-RPN-010 is a single-artifact move plus reference update batch.

References to update during future execution:

- SDD Modes active dossier and Specification references.
- Global capability/spec indexes.
- Active RPN package references and route registry.
- Any new references introduced after this map must be re-scanned immediately before execution.

References to keep historical:

- Closed capability handovers, context refs, evidence indexes and retrospective validation reports unless a separate re-entry decision authorizes rewriting.

### File-level reference inventory for Architecture route

| Source artifact | Reference role | Future handling under Option A |
| --- | --- | --- |
| `docs/capabilities/sdd-modes/tasks.md` | Active SDD Modes dossier reference. | Update to `specs/capabilities/sdd-modes/arch-001-sdd-modes.md`. |
| `docs/capabilities/sdd-modes/context_refs.md` | Active SDD Modes context index. | Update to target path. |
| `docs/capabilities/sdd-modes/sdd_readiness_assessment.md` | Active SDD Modes readiness evidence. | Update active route rows to target path; preserve historical wording if explicitly describing prior state. |
| `specs/capabilities/sdd-modes/spec-001-sdd-modes.md` | Active SDD Modes Specification reference to Architecture. | Update to target path. |
| `docs/capabilities/index.md` | Global routing catalog. | Update SDD Modes Architecture route to target path. |
| `specs/capabilities/index.md` | Global specs catalog. | Update SDD Modes Architecture route to target path. |
| `docs/capabilities/repository-physical-normalization/project_brief.md` | Active RPN governance and decision trace. | Update live route decision references after execution; keep historical T-022/T-028 references where needed. |
| `docs/capabilities/repository-physical-normalization/context_refs.md` | Active RPN context index. | Update live route decision references after execution. |
| `docs/capabilities/repository-physical-normalization/sdd_readiness_assessment.md` | Active RPN readiness and gate evidence. | Update live route decision references after execution; preserve historical gate language. |
| `docs/capabilities/repository-physical-normalization/tasks.md` | Active RPN task plan and decision log. | Update DEV-RPN-010 status after future execution; preserve T-022/T-028 history. |
| `specs/capabilities/repository-physical-normalization/spec-001-repository-physical-normalization.md` | Active RPN specification dependencies/open questions. | Update open question/decision once Reviewer, QA and human authorization close it. |
| `specs/capabilities/repository-physical-normalization/arch-001-repository-physical-normalization.md` | Active RPN architecture. | Update AD-004/P4 from deferred to proposed/executed state only when authorized. |
| `docs/capabilities/repository-physical-normalization/governed-execution-preparation/*.md` | Active RPN execution-prep package. | Update DEV-RPN-010 package status through Reviewer, QA and execution if authorized. |
| `specs/spec-001-sdd-modes.architecture.md` | Artifact to move. | Move to target path only after authorization; root path becomes stub. |
| `docs/capabilities/project-consolidation-and-closure/context_refs.md` | Closed capability context; historical route. | Keep historical; legacy stub resolves navigation. |
| `docs/capabilities/project-consolidation-and-closure/project_brief.md` | Closed capability brief; historical route. | Keep historical; legacy stub resolves navigation. |
| `specs/capabilities/project-consolidation-and-closure/spec-001-sdd-project-consolidation-and-closure.md` | Closed specification; historical route. | Keep historical; legacy stub resolves navigation. |
| `docs/capabilities/foundation-derivation-and-project-initialization/context_refs.md` | Closed capability context; historical route. | Keep historical; legacy stub resolves navigation. |
| `specs/capabilities/foundation-derivation-and-project-initialization/spec-001-foundation-derivation-and-project-initialization.md` | Closed specification; historical route. | Keep historical; legacy stub resolves navigation. |
| `specs/capabilities/foundation-derivation-and-project-initialization/arch-001-foundation-derivation-and-project-initialization.md` | Closed architecture; historical route. | Keep historical; legacy stub resolves navigation. |
| `docs/capabilities/consolidation-agent/context_refs.md` | Closed capability context; historical route. | Keep historical; legacy stub resolves navigation. |
| `docs/capabilities/consolidation-agent/tasks.md` | Closed capability task/evidence trace. | Keep historical; legacy stub resolves navigation. |
| `docs/capabilities/consolidation-agent/validations/sdd-modes-retrospective/consolidation_report.md` | Retrospective evidence of old layout. | Keep unchanged; legacy stub resolves navigation. |
| `docs/capabilities/consolidation-agent/validations/sdd-modes-retrospective/evidence_index.md` | Retrospective evidence index. | Keep unchanged; legacy stub resolves navigation. |
| `docs/capabilities/consolidation-agent/validations/sdd-modes-retrospective/qa_gate_decision.md` | QA evidence of prior baseline. | Keep unchanged; legacy stub resolves navigation. |
| `docs/capabilities/consolidation-agent/validations/sdd-modes-retrospective/validation_handover.md` | Validation handover evidence. | Keep unchanged; legacy stub resolves navigation. |

Completeness note:

This inventory is based on the repository-wide `rg` scan run during T-029. Any future execution must rerun the same scan immediately before DEV-RPN-010 because this preparation itself introduces additional active RPN references to the proposed target path.