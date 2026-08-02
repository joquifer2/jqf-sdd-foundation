# Indice de capacidades

## Proposito

Este archivo es un catalogo ligero de capacidades SDD trazadas en esta Foundation.

Sirve como ayuda de routing y trazabilidad.

No es una specification normativa, no sustituye los expedientes de capacidad y no autoriza Development.

---

## Catalogo

| Capacidad | Estado | SDD Mode | Documentos principales | Specs principales | Siguiente paso valido |
| --- | --- | --- | --- | --- | --- |
| SDD Modes | Baseline cerrado / normalized first wave | SDD Full | `docs/capabilities/sdd-modes/project_brief.md`; `docs/capabilities/sdd-modes/context_refs.md`; `docs/capabilities/sdd-modes/tasks.md`; `docs/capabilities/sdd-modes/sdd_readiness_assessment.md` | `specs/capabilities/sdd-modes/spec-001-sdd-modes.md`; `specs/spec-001-sdd-modes.architecture.md` | Rutas legacy conservadas como stubs; Architecture legacy permanece en ruta original hasta decision futura. |
| SDD Project Consolidation and Closure | Closed | SDD Full | `docs/capabilities/project-consolidation-and-closure/project_brief.md`; `docs/capabilities/project-consolidation-and-closure/context_refs.md`; `docs/capabilities/project-consolidation-and-closure/tasks.md`; `docs/capabilities/project-consolidation-and-closure/sdd_readiness_assessment.md`; `docs/capabilities/project-consolidation-and-closure/closure_handover.md`; `docs/capabilities/project-consolidation-and-closure/evidence_index.md`; `docs/capabilities/project-consolidation-and-closure/residual_debt.md` | `specs/capabilities/project-consolidation-and-closure/spec-001-sdd-project-consolidation-and-closure.md`; `specs/capabilities/project-consolidation-and-closure/arch-001-sdd-project-consolidation-and-closure.md` | No hay siguiente paso activo; el trabajo futuro requiere una nueva capacidad SDD o decision explicita de reentrada. |
| Foundation Derivation and Project Initialization | Closed | SDD Full | `docs/capabilities/foundation-derivation-and-project-initialization/project_brief.md`; `docs/capabilities/foundation-derivation-and-project-initialization/context_refs.md`; `docs/capabilities/foundation-derivation-and-project-initialization/tasks.md`; `docs/capabilities/foundation-derivation-and-project-initialization/sdd_readiness_assessment.md`; `docs/capabilities/foundation-derivation-and-project-initialization/closure_handover.md`; `docs/capabilities/foundation-derivation-and-project-initialization/residual_debt.md` | `specs/capabilities/foundation-derivation-and-project-initialization/spec-001-foundation-derivation-and-project-initialization.md`; `specs/capabilities/foundation-derivation-and-project-initialization/arch-001-foundation-derivation-and-project-initialization.md` | No hay siguiente paso activo; reentrada mediante handover/deuda residual o nueva capacidad SDD. Development permanece no autorizado. |
| Consolidation Agent | Closed with conditions | SDD Full | `docs/capabilities/consolidation-agent/project_brief.md`; `docs/capabilities/consolidation-agent/context_refs.md`; `docs/capabilities/consolidation-agent/tasks.md`; `docs/capabilities/consolidation-agent/sdd_readiness_assessment.md`; `docs/capabilities/consolidation-agent/evidence_index.md`; `docs/capabilities/consolidation-agent/residual_debt.md`; `docs/capabilities/consolidation-agent/closure_handover.md`; `docs/capabilities/consolidation-agent/global_closure_coherence_gate.md`; `docs/capabilities/consolidation-agent/validations/sdd-modes-retrospective/validation_closure.md`; `docs/capabilities/consolidation-agent/validations/sdd-modes-retrospective/qa_gate_decision.md` | `specs/capabilities/consolidation-agent/spec-001-consolidation-agent.md`; `specs/capabilities/consolidation-agent/arch-001-consolidation-agent.md`; `.github/agents/consolidation.agent.md` | No queda siguiente agente activo dentro de esta capacidad. Development adicional permanece no autorizado. Siguiente capacidad posible: Repository Physical Normalization, solo con decision humana explicita. |
| Repository Physical Normalization | Development first wave executed / pending review | SDD Full | `docs/capabilities/repository-physical-normalization/project_brief.md`; `docs/capabilities/repository-physical-normalization/context_refs.md`; `docs/capabilities/repository-physical-normalization/tasks.md`; `docs/capabilities/repository-physical-normalization/sdd_readiness_assessment.md`; `docs/capabilities/repository-physical-normalization/governed-execution-preparation/README.md`; `docs/capabilities/repository-physical-normalization/governed-execution-preparation/movement_execution_report.md` | `specs/capabilities/repository-physical-normalization/spec-001-repository-physical-normalization.md`; `specs/capabilities/repository-physical-normalization/arch-001-repository-physical-normalization.md` | Siguiente paso valido: Reviewer Agent sobre ejecucion Development del primer lote. Development autorizado solo para el lote ejecutado; ejecucion adicional requiere decision/gate aplicable. |

---

## Reglas

- Los expedientes de capacidad siguen siendo la fuente de trazabilidad especifica de cada capacidad.
- Las specifications y gates aprobados siguen siendo las fuentes normativas de requisitos y decisiones de fase.
- Los artefactos de baseline cerrado no deben moverse, sobrescribirse ni reclasificarse sin aprobacion humana explicita.
- `Development` permanece no autorizado salvo que una decision humana futura y un gate aplicable digan lo contrario.