# Architecture

## Metadatos

### Architecture ID

ARCH-001

### Spec relacionada

SPEC-001 - Repository Physical Normalization

### Title

Repository Physical Normalization Documentary Architecture

### Estado

Closed - DEV-RPN-010

### Responsable

Jordi Quiroga

### Ultima actualizacion

2026-08-02

### Template

No existe una plantilla oficial de arquitectura To-Be en este repositorio. Este artefacto usa una estructura inferida a partir de `.github/agents/architect.agent.md` y permanece en alcance conceptual/documental.

---

## 1. Solution Summary

`Repository Physical Normalization` define una arquitectura documental para transformar, en una fase futura autorizada, la estructura fisica de `jqf-sdd-foundation` sin alterar baselines cerrados, sin romper trazabilidad y sin convertir propuestas en ejecucion automatica.

Esta Architecture no mueve, copia, renombra, elimina ni sustituye archivos. No crea scripts, tools, workflows, runtime ni automatizaciones. Define componentes, interfaces, decisiones, alternativas y planes documentales que una fase posterior debera revisar antes de cualquier ejecucion.

---

## 2. Architectural Objective

Definir una estructura arquitectonica documental que permita:

- separar baseline global, baseline de capacidad, expediente historico, evidencia y documentacion transversal;
- aplicar la normalizacion futura en lotes pequenos, reversibles y trazables;
- convertir propuestas `proposal-only` del `Consolidation Agent` en planes revisables, no en cambios aplicados;
- usar `SDD Modes` como primer caso de aplicacion futura sin modificarlo ahora;
- mantener compatibilidad con referencias, agentes y repositorios derivados;
- establecer los artefactos minimos que deben existir antes de ejecutar cualquier movimiento futuro.

---

## 3. Specification Decisions Reflected

| Specification decision | Architectural reflection |
| --- | --- |
| Normalizacion fisica no cambia semantica | Se separa `Physical Relocation Plan` de decisiones normativas de baseline. |
| Una ruta canonica por artefacto | Se introduce `Canonical Route Registry` como componente conceptual. |
| Compatibilidad antes que limpieza | Se selecciona estrategia de compatibilidad con stubs documentales temporales. |
| Reference map obligatorio | Se define `Reference Map` como artefacto requerido antes de ejecucion. |
| Rollback obligatorio | Se define `Rollback Plan` y lotes de cambio reversibles. |
| SDD Modes es primer caso futuro | Se crea `SDD Modes Pilot Package` como blueprint documental no ejecutado. |
| Consolidation Agent propone, no ejecuta | Se define interfaz entre `Consolidation Proposal` y `Normalization Architecture`. |
| Development no autorizado | La arquitectura queda en Documentation/Architecture; no ejecuta cambios. |

---

## 4. Main Components

| Componente | Responsabilidad | Estado |
| --- | --- | --- |
| Physical Taxonomy Model | Clasifica artefactos por baseline global, baseline de capacidad, expediente, evidencia, templates, agentes y transversalidad. | Definido conceptualmente. |
| Canonical Route Registry | Determina ruta canonica vigente y rutas legacy para cada artefacto afectado. | Propuesto; no creado como archivo separado. |
| Reference Map | Inventario de referencias que deben actualizarse o compatibilizarse antes de mover. | Definido como artefacto futuro. |
| Movement Plan | Define acciones futuras: move, copy, keep, archive, replace, stub. | Definido como artefacto futuro. |
| Compatibility Layer | Mantiene navegacion desde rutas legacy mediante stubs o indices durante transicion. | Seleccionado conceptualmente. |
| Rollback Plan | Describe vuelta atras por lote si se detectan referencias rotas o ambiguedad. | Definido como artefacto futuro. |
| Validation Checklist | Verifica enlaces, indices, context loading, ausencia de baseline mutation y ausencia de ejecucion no autorizada. | Definido conceptualmente. |
| SDD Modes Pilot Package | Primer lote futuro de normalizacion sobre artefactos raiz de `SDD Modes`. | Blueprint no ejecutado. |
| Derived Project Compatibility Notes | Registra impacto y orientacion para repositorios derivados si cambian rutas exportables. | Condicional. |

---

## 5. Component Responsibilities

### 5.1 Physical Taxonomy Model

Debe clasificar cada artefacto afectado antes de proponer ubicacion fisica.

Categorias obligatorias:

- `global-canonical-baseline`;
- `capability-canonical-baseline`;
- `closed-methodological-dossier`;
- `historical-evidence`;
- `residual-debt-and-reentry`;
- `template-baseline`;
- `agent-definition-baseline`;
- `adapter-baseline`;
- `transversal-documentation`;
- `legacy-route-stub`.

La categoria no se infiere solo desde la ruta fisica. Debe apoyarse en estado, fuente canonica, handover, spec, gate o decision humana.

### 5.2 Canonical Route Registry

Debe responder, para cada artefacto afectado:

- ruta actual;
- ruta canonica propuesta;
- categoria documental;
- estado del artefacto;
- fuente que justifica la ruta canonica;
- si requiere stub legacy;
- si requiere actualizacion de indices;
- si debe cargarse por defecto por futuros agentes.

En esta Architecture el registry queda embebido como modelo y no se crea archivo standalone.

### 5.3 Reference Map

Debe inventariar referencias antes de cualquier cambio futuro.

Cobertura minima:

- enlaces Markdown relativos o absolutos;
- rutas inline en tablas, listas y texto;
- referencias en `context_refs.md`;
- referencias en handovers, evidence indexes y residual debt;
- indices `docs/capabilities/index.md` y `specs/capabilities/index.md`;
- `README.md`, `AGENTS.md` y `.github/instructions/sdd.instructions.md`;
- definiciones de agentes `.github/agents/`;
- adaptadores `.codex/agents/`;
- gates y templates.

Salida conceptual:

| Campo | Descripcion |
| --- | --- |
| Reference ID | ID estable de referencia. |
| Source artifact | Archivo donde aparece la referencia. |
| Referenced path | Ruta actual referenciada. |
| Reference kind | Markdown link / inline path / table entry / instruction / historical mention. |
| Proposed handling | update / keep historical / stub-compatible / investigate. |
| Blocking? | Si bloquea movimiento futuro. |

### 5.4 Movement Plan

Debe convertir el registry y el reference map en acciones futuras.

Acciones permitidas:

- `move`: relocation futura de un artefacto manteniendo contenido aprobado;
- `copy-derived`: crear resumen, handover, evidence index o residual debt derivado;
- `keep`: conservar ruta vigente;
- `archive`: marcar como historico o superseded sin borrar;
- `replace-with-stub`: sustituir contenido navegable por stub que apunta a ruta canonica;
- `defer`: posponer por riesgo, falta de referencia o decision pendiente.

Cada accion futura debe incluir:

- precondicion;
- agente responsable propuesto;
- artefactos afectados;
- referencias a actualizar;
- compatibilidad legacy;
- criterio de validacion;
- rollback.

### 5.5 Compatibility Layer

La compatibilidad se resuelve mediante `routing stubs` documentales temporales, no mediante alias de filesystem ni automatizaciones.

Un stub debe:

- declarar que no es fuente normativa;
- apuntar a la ruta canonica vigente;
- conservar contexto minimo de por que existe;
- indicar fecha, decision y owner del movimiento futuro;
- listar restricciones si el artefacto movido pertenece a baseline cerrado.

No se crean stubs en esta Architecture.

### 5.6 Rollback Plan

Debe existir antes de ejecutar cualquier lote futuro.

Contenido minimo:

- lote de cambio;
- rutas antes/despues;
- stubs creados;
- indices actualizados;
- referencias modificadas;
- criterio para revertir;
- responsable de revertir;
- decision/gate que autoriza rollback;
- validacion posterior al rollback.

El rollback no puede borrar evidencia ni ocultar deuda.

### 5.7 Validation Checklist

Debe validar:

- todas las rutas canonicas aparecen en indices o handovers aplicables;
- ninguna ruta legacy queda como segunda fuente canonica;
- las referencias historicas estan etiquetadas como historicas si conservan rutas antiguas;
- los agentes pueden localizar la fuente vigente desde context refs o indices;
- no se modifico contenido normativo de capacidades cerradas;
- no se eliminaron archivos sin autorizacion especifica;
- no se introdujeron scripts, tools, workflows ni runtime;
- el lote puede revertirse.

### 5.8 SDD Modes Pilot Package

Blueprint futuro para primer lote controlado.

Debe tratar los artefactos raiz de `SDD Modes` como read-only hasta que se autorice ejecucion.

Artefactos candidatos:

| Current path | Target path | Action | Compatibility |
| --- | --- | --- | --- |
| `docs/capabilities/sdd-modes/project_brief.md` | `docs/capabilities/sdd-modes/project_brief.md` | move future | root stub required |
| `docs/capabilities/sdd-modes/context_refs.md` | `docs/capabilities/sdd-modes/context_refs.md` | move future | root stub required |
| `docs/capabilities/sdd-modes/tasks.md` | `docs/capabilities/sdd-modes/tasks.md` | move future | root stub required |
| `docs/capabilities/sdd-modes/sdd_readiness_assessment.md` | `docs/capabilities/sdd-modes/sdd_readiness_assessment.md` | move future | root stub required |
| `specs/capabilities/sdd-modes/spec-001-sdd-modes.md` | `specs/capabilities/sdd-modes/spec-001-sdd-modes.md` | move future | root stub required |
| `specs/spec-001-sdd-modes.architecture.md` | Decision pending | defer | keep current path until naming decision |

Derived artifacts possible, not executed:

- `docs/capabilities/sdd-modes/closure_handover.md`;
- `docs/capabilities/sdd-modes/evidence_index.md`;
- `docs/capabilities/sdd-modes/residual_debt.md`.

---

## 6. Relationships and Interfaces

### 6.1 Architecture Flow

```text
SPEC-001
  -> Architecture authorization
  -> ARCH-001
  -> Reviewer Agent
  -> QA Gate Agent
  -> Human decision on any future execution
```

This Architecture does not advance directly to Development.

### 6.2 Normalization Preparation Flow

```text
Closed capability / proposal-only package
  -> Physical Taxonomy Model
  -> Canonical Route Registry
  -> Reference Map
  -> Movement Plan
  -> Compatibility Layer plan
  -> Rollback Plan
  -> Review + QA
  -> Human decision before execution
```

### 6.3 Consolidation Agent Interface

Input from `Consolidation Agent`:

- artifact classification proposal;
- baseline/dossier/evidence/debt inventory;
- movement proposal;
- risks and re-entry points.

Architecture response:

- accepts proposal as evidence only;
- translates it into governed registry/map/plan;
- identifies unresolved decisions;
- blocks execution until review, QA and human approval.

### 6.4 Documentation Agent Interface

Documentation Agent may update catalogues, references and stubs only when the relevant phase authorizes it.

During Architecture, Documentation Agent may help prepare:

- non-executable reference maps;
- non-executable movement plans;
- documentation impact tables;
- draft stubs as examples.

It may not apply physical movement during this Architecture.

### 6.5 Reviewer and QA Interface

Reviewer must evaluate:

- consistency with SPEC-001;
- whether reference map and movement plan are sufficiently explicit;
- whether any physical execution leaked into Architecture.

QA Gate must evaluate:

- Architecture readiness;
- conditions for any future phase;
- no Development authorization;
- no baseline mutation.

---

## 7. Target Documentary Structure

The selected conceptual target remains capability-scoped dossiers plus global/transversal surfaces.

```text
docs/
  capabilities/
    index.md
    <capability-id>/
      project_brief.md
      context_refs.md
      tasks.md
      sdd_readiness_assessment.md
      closure_handover.md
      evidence_index.md
      residual_debt.md
      validations/
  templates/
  glosario_terminos.md

specs/
  capabilities/
    index.md
    <capability-id>/
      spec-001-<capability-id>.md
      arch-001-<capability-id>.md
  templates/

.github/
  agents/
  instructions/
  prompts/
  skills/

.codex/
  agents/

gates/
README.md
AGENTS.md
```

Decision: do not introduce `docs/baseline/` or `specs/baseline/` in the first normalization architecture.

Rationale:

- current baseline is already distributed across specs, instructions, agents, gates, templates and glosario;
- adding `baseline/` now would create extra routing complexity;
- a future capacity can revisit baseline folders if evidence shows current routing is insufficient.

---

## 8. Reference Map Architecture

### 8.1 Map generation rule

A future reference map must be generated before any movement. It can be created manually or with future approved tooling, but this Architecture does not create tooling.

### 8.2 Reference classes

| Class | Handling |
| --- | --- |
| Canonical active reference | Update to new canonical path when move is authorized. |
| Historical reference | Keep old path and label as historical if it describes past state. |
| Gate evidence reference | Update only if evidence artifact moves; preserve decision text. |
| Agent loading reference | Must resolve after migration through context refs, indices or stubs. |
| Template reference | Keep if template describes generic path; update if it points to concrete moved artifact. |
| External reference | Do not rewrite unless explicitly owned by this repo. |

### 8.3 Minimum reference surfaces for SDD Modes pilot

Before moving `SDD Modes`, inspect at least:

- `README.md`;
- `AGENTS.md`;
- `.github/instructions/sdd.instructions.md`;
- `.github/agents/*.agent.md`;
- `.codex/agents/*.toml` and README files;
- `docs/capabilities/index.md`;
- `specs/capabilities/index.md`;
- all `docs/capabilities/*/context_refs.md`;
- all `closure_handover.md`, `evidence_index.md`, `residual_debt.md`;
- all `tasks.md` and `sdd_readiness_assessment.md` files;
- all specs and architectures.

---

## 9. Movement Plan Architecture

### 9.1 First execution wave principle

The first future execution wave should be limited to `SDD Modes` root dossier normalization and only after review, QA and human approval.

### 9.2 Recommended SDD Modes phases

| Phase | Purpose | Execution status |
| --- | --- | --- |
| P0 - Inventory | Build reference map and canonical route registry. | Future, not executed. |
| P1 - Derived summaries | Create optional capability-local handover/evidence/debt files if approved. | Future, not executed. |
| P2 - Move low-risk docs | Move root docs to `docs/capabilities/sdd-modes/` with stubs. | Future, not executed. |
| P3 - Move spec | Move `specs/capabilities/sdd-modes/spec-001-sdd-modes.md` with stub. | Future, not executed. |
| P4 - Decide architecture filename | Keep legacy architecture path or move to `arch-001-sdd-modes.md`. | Future decision. |
| P5 - Validate | Check references, stubs, indices, agent loading and rollback. | Future, not executed. |

### 9.3 Architecture filename decision

Decision: defer renaming `specs/spec-001-sdd-modes.architecture.md`.

Rationale:

- it is a high-reference artifact;
- renaming introduces more compatibility cost than moving lower-risk docs;
- the future movement plan should first measure references;
- keeping the legacy filename may be acceptable if it reduces risk.

---

## 10. Rollback Architecture

Rollback must be possible per phase.

| Rollback target | Trigger | Response |
| --- | --- | --- |
| Broken links after move | Link/reference validation fails. | Restore previous path or adjust stub/index before proceeding. |
| Ambiguous canonical route | Both old and new paths appear normative. | Mark one route canonical, convert other to stub, or revert. |
| Agent loading failure | Agent cannot locate required context. | Restore routing through context refs/index/stub. |
| Unexpected baseline mutation | Content diff changes normative text. | Revert content change; movement only may proceed after review. |
| Scope creep into automation | Script/tool/workflow appears. | Stop phase; return to Specification or separate Development capability. |

Rollback evidence must be recorded in tasks/readiness or a future movement report.

---

## 11. Dependencies

- `docs/capabilities/repository-physical-normalization/project_brief.md`
- `docs/capabilities/repository-physical-normalization/context_refs.md`
- `specs/capabilities/repository-physical-normalization/spec-001-repository-physical-normalization.md`
- `docs/capabilities/repository-physical-normalization/sdd_readiness_assessment.md`
- `docs/capabilities/repository-physical-normalization/tasks.md`
- `docs/capabilities/consolidation-agent/validations/sdd-modes-retrospective/consolidation_report.md`
- `docs/capabilities/consolidation-agent/validations/sdd-modes-retrospective/qa_gate_decision.md`
- `docs/capabilities/consolidation-agent/closure_handover.md`
- `docs/capabilities/project-consolidation-and-closure/closure_handover.md`
- `specs/capabilities/project-consolidation-and-closure/arch-001-sdd-project-consolidation-and-closure.md`
- `.github/instructions/sdd.instructions.md`
- `AGENTS.md`

---

## 12. Constraints

- No Development.
- No physical movement.
- No file copy as migration execution.
- No rename.
- No deletion.
- No replacement of existing files with stubs in this phase.
- No scripts, tools, workflows, runtime or automation.
- No baseline mutation.
- No closure of residual debt.
- No change to closed capabilities except local references/index updates authorized for this Architecture package.

---

## 13. Alternatives Considered

### Alternative A - Create `docs/baseline/` and `specs/baseline/` now

Status: Rejected for first Architecture.

Pros:

- explicit baseline area;
- potential future clarity for loading canonical artifacts.

Cons:

- adds a new concept not yet proven necessary;
- could duplicate existing source-of-truth routing;
- increases migration complexity for first pilot.

### Alternative B - Capability dossiers plus global indices

Status: Selected.

Pros:

- matches current capability structure;
- minimizes conceptual additions;
- keeps global/transversal artifacts in place;
- supports SDD Modes migration without reorganizing the whole repo.

Cons:

- baseline remains distributed;
- requires disciplined indices and handovers.

### Alternative C - Archive legacy root paths without stubs

Status: Rejected.

Pros:

- cleaner root.

Cons:

- high risk of broken references;
- poor compatibility for agents and derived repos;
- suggests history was removed rather than rerouted.

### Alternative D - Keep all SDD Modes root paths indefinitely

Status: Not selected as target, allowed as fallback.

Pros:

- zero movement risk;
- preserves current references.

Cons:

- leaves physical/logical mismatch unresolved;
- keeps root docs looking like active global project artifacts.

---

## 14. Architectural Decisions

### AD-001 - Use capability-scoped dossiers as target

Decision: Future normalized capabilities should live under `docs/capabilities/<capability-id>/` and `specs/capabilities/<capability-id>/` unless explicitly transversal.

### AD-002 - Do not introduce baseline folders in first wave

Decision: `docs/baseline/` and `specs/baseline/` remain future considerations, not part of first target.

### AD-003 - Use stubs for legacy compatibility

Decision: Future movement should keep root routing stubs for SDD Modes until references and derived expectations are validated.

### AD-004 - Defer SDD Modes architecture filename rename

Decision: Do not decide rename of `spec-001-sdd-modes.architecture.md` until reference map proves it is low-risk.

### AD-005 - Treat derived SDD Modes artifacts as summaries, not new closure

Decision: Future `closure_handover.md`, `evidence_index.md` and `residual_debt.md` for SDD Modes, if created, must summarize and route; they must not rewrite closure decisions.

### AD-006 - No execution from Architecture

Decision: This Architecture prepares a design and future plans only. Any execution requires later review, QA and human approval.

---

## 15. Risks

| Risk | Impact | Mitigation |
| --- | --- | --- |
| Architecture interpreted as movement approval | High | Repeated no-execution constraints and future approval requirements. |
| Stubs become second source of truth | High | Stub format must declare non-normative routing only. |
| Reference map misses inline paths | High | Require broad surfaces and reviewer validation. |
| Baseline folders become premature abstraction | Medium | Reject for first wave; revisit only if evidence supports. |
| SDD Modes closure is accidentally rewritten | High | Derived summaries cannot change closure decisions. |
| Derived repositories depend on old paths | Medium | Keep stubs and add compatibility notes if needed. |
| Automation sneaks into normalization | High | Treat tooling as separate future Development capability. |

---

## 16. Impact on Existing Architecture

| Surface | Impact | Required action |
| --- | --- | --- |
| `docs/capabilities/index.md` | References ARCH-001 as catalog routing. | Completed; no normative effect. |
| `specs/capabilities/index.md` | Indexes ARCH-001 as catalog routing. | Completed; no normative effect. |
| `README.md` | Future update may describe normalized structure after execution, not now. | No immediate action. |
| `.github/instructions/sdd.instructions.md` | Future update may add physical normalization rule after closure. | No immediate action. |
| `AGENTS.md` | No change; agent boundaries remain valid. | No action. |
| `Consolidation Agent` | Provides proposal input only. | No change to closed baseline. |
| `SDD Modes` root artifacts | Pilot target future only. | No movement or content change. |
| Templates | Future movement/reference/rollback templates may be useful. | Future Documentation consideration. |
| Gates | Existing review/QA gates suffice for Architecture; execution may need dedicated gate later. | Future QA consideration. |

---

## 17. Open Architectural Questions

- What exact stub template should be used during future execution?
- Should future movement reports be standalone files or sections in `tasks.md` / readiness?
- How long should legacy stubs remain after SDD Modes movement?
- Should derived repositories receive a migration note or is Foundation-local routing sufficient?
- What minimum link/reference validation is acceptable without automation?
- Does a later phase need a dedicated `Physical Normalization Execution Gate`?

---

## 18. Next Recommended Step

```text
No active next step. DEV-RPN-010 closed by human decision.
```

This supersedes the historical Architecture next step after T-013, T-021 and T-028 for the DEV-RPN-010 decision package.

Development remains `NOT AUTHORIZED`.

No physical normalization is authorized.

---

## Definition of Done

This Architecture is ready for QA Gate review when:

- main components are identified;
- component responsibilities are defined;
- interfaces are documented;
- dependencies and constraints are explicit;
- alternatives and architectural decisions are recorded;
- SDD Modes pilot approach is defined without execution;
- reference map, movement plan and rollback plan are defined as future documentary artifacts;
- no file movement, copy, rename, deletion, script, workflow, tool or runtime is introduced.
---

## 20. Governed Execution Preparation Note

Fecha: 2026-08-02.

Tras QA Gate T-012, una decision humana autorizo la fase `Governed Execution Preparation` solo para crear el paquete documental definitivo previo a una posible decision futura de Development.

Paquete documental preparado en:

`docs/capabilities/repository-physical-normalization/governed-execution-preparation/README.md`

Esta nota no modifica las decisiones arquitectonicas de `ARCH-001`, no autoriza Development, no ejecuta movimientos fisicos, no crea stubs y no modifica baselines cerrados.
---

## 21. SDD Modes Architecture Route Decision

Fecha: 2026-08-02.

Decision arquitectonica propuesta:

`Option A`.

Mover en una futura ola autorizada:

```text
specs/spec-001-sdd-modes.architecture.md
  -> specs/capabilities/sdd-modes/arch-001-sdd-modes.md
```

Compatibilidad:

La ruta raiz `specs/spec-001-sdd-modes.architecture.md` debe convertirse en stub no normativo tras el movimiento.

Rationale:

- alinea SDD Modes con `specs/capabilities/<capability-id>/arch-001-<capability-id>.md`;
- evita una excepcion canonica permanente;
- las referencias activas son actualizables;
- las referencias historicas quedan protegidas por stub legacy;
- rollback es viable por tratarse de un movimiento acotado.

Decision alternativa B:

Rechazada como objetivo recomendado. Mantener la ruta raiz como excepcion canonica permanente preservaria compatibilidad inmediata, pero mantendria deuda fisica y una regla especial de carga sin necesidad demostrada.

Estado:

QA passed with minor conditions by T-038. Reviewer T-033, QA Gate T-034, human authorization T-035, execution T-036 and Reviewer T-037 preceded the post-execution QA decision.