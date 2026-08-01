# Architecture

## Metadata

### Architecture ID

ARCH-001

### Related Spec

SPEC-001 - SDD Modes

### Title

SDD Modes Conceptual and Documentary Architecture

### Status

Draft

### Owner

Jordi Quiroga

### Last Updated

2026-07-31

### Template

No existe una plantilla oficial de arquitectura To-Be en este repositorio. Este artefacto usa una estructura inferida a partir de `.github/agents/architect.agent.md` y permanece en alcance conceptual/documental.

---

## 1. Solution Summary

SDD Modes introduce una capa de gobierno proporcional dentro del SDD Harness de `jqf-sdd-foundation`.

La arquitectura no crea runtime, workflows ejecutables, tools, integraciones, infraestructura ni logica de negocio. Define como deben organizarse documentalmente las reglas aprobadas por `SPEC-001` para que repositorios derivados puedan declarar y aplicar uno de tres modos oficiales:

- `SDD Minimal`
- `SDD Lite`
- `SDD Full`

`SDD Modes` no es un harness separado ni un sistema operativo. Es una extension documental de gobierno del SDD Harness.

---

## 2. Architectural Objective

Definir una estructura conceptual y documental que soporte:

- un modelo de gobierno proporcional dentro de la Foundation;
- un unico catalogo de agentes metodologicos;
- declaracion inicial del modo en `Project Brief`;
- trazabilidad de seleccion, escalado, reduccion, checks, gates, evidencia y validacion;
- compatibilidad hacia atras mediante `Undeclared`;
- separacion clara entre reglas normativas, indices de contexto, plantillas, instrucciones de agentes y evidencia.

La arquitectura preserva el estado SDD vigente: Specification / Structure.

---

## 3. Decisiones de Specification Reflejadas

Esta arquitectura refleja decisiones humanas cerradas en `SPEC-001` y `docs/tasks.md` T-002 a T-010. No las inventa ni las resuelve por inferencia.

| Decision | Reflejo arquitectonico |
| --- | --- |
| `SDD Mode` es el termino normativo | Los componentes usan `Mode` como unidad conceptual, no `Profile` ni `Governance Mode`. |
| Modos oficiales: `SDD Minimal`, `SDD Lite`, `SDD Full` | La taxonomia mantiene exactamente tres modos oficiales iniciales. |
| `Project Brief` es fuente canonica inicial | El componente Mode Declaration se ancla inicialmente en `Project Brief`. |
| `docs/context_refs.md` no es fuente normativa del modo | Context References queda como indice y routing de contexto, no como policy de modo. |
| `Undeclared` existe como estado temporal | Compatibility Policy trata `Undeclared` como estado, no como cuarto modo. |
| Seleccion por juicio humano | Mode Selection Criteria organiza dimensiones sin scoring automatico. |
| Checks ligeros consolidados | Checks and Gates Policy evita archivo por microtarea y separa checks de gates. |
| Evidencia consolidada | Evidence Policy ubica evidencia en artefacto de trabajo, decision, hito o gate. |
| Unidad normativa: `incremento gobernado` | Lifecycle, tasks, checks, gates y evidencia se articulan alrededor de incrementos gobernados. |
| Escenarios VAL-001 a VAL-004 | Validation Scenarios queda estructurado por escenarios; repos concretos siguen `PENDING`. |

---

## 4. Main Components

| Component | Responsibility | Status |
| --- | --- | --- |
| Mode Taxonomy | Define los tres modos oficiales y su semantica aprobada. | Definido por `SPEC-001`. |
| Mode Declaration | Registra modo, justificacion, owner, fecha, condiciones de riesgo y disparadores de reevaluacion. | Fuente inicial: `Project Brief`. |
| Mode Selection Criteria | Organiza dimensiones de seleccion para juicio humano documentado. | Definido sin scoring automatico. |
| Mode Lifecycle Rules | Define declaracion inicial, reevaluacion, escalado, reduccion y `Undeclared`. | Parcialmente definido; aprobadores/cadencia siguen abiertos. |
| Artifact Applicability Matrix | Clasifica artefactos por modo como obligatorios, condicionales, recomendados, opcionales o no habituales. | Requiere desarrollo documental posterior. |
| Agent Intervention Matrix | Define como agentes existentes adaptan intensidad por modo sin duplicarse. | Requiere desarrollo documental posterior. |
| Checks and Gates Policy | Separa checks ligeros de gates formales y define condiciones de elevacion. | Definido conceptualmente por `SPEC-001`. |
| Evidence Policy | Define consolidacion de evidencia por modo e incremento gobernado. | Definido conceptualmente por `SPEC-001`. |
| Compatibility Policy | Define comportamiento de repositorios existentes sin modo declarado. | `Undeclared` definido por `SPEC-001`. |
| Validation Scenarios | Define casos VAL-001 a VAL-004 para validar la capacidad. | Escenarios definidos; repos concretos `PENDING`. |

---

## 5. Component Responsibilities

### 5.1 Mode Taxonomy

Mode Taxonomy contiene las definiciones aprobadas de `SDD Minimal`, `SDD Lite` y `SDD Full`.

Debe expresar:

- `SDD Minimal`: exploracion, pruebas internas o cambios documentales/acotados de bajo riesgo;
- contextos prohibidos para Minimal: datos sensibles, produccion, cumplimiento, integraciones criticas, impacto operacional alto, seguridad/privacy relevantes, multiples stakeholders criticos o baja reversibilidad;
- `SDD Lite`: MVPs, herramientas internas o primeras versiones de riesgo controlado con trazabilidad, checks, hitos y validacion humana;
- `SDD Full`: baseline vigente completo de `jqf-sdd-foundation`.

### 5.2 Mode Declaration

Mode Declaration hace visible y revisable el modo seleccionado.

La fuente canonica inicial es `Project Brief`.

Debe capturar:

- modo seleccionado;
- justificacion humana;
- owner;
- fecha;
- condiciones relevantes de riesgo;
- controles adicionales requeridos pese al modo;
- disparadores de reevaluacion.

Los cambios posteriores de modo deben vivir en el artefacto de decision o gate aprobado que autorice el cambio. `docs/context_refs.md` debe indexar la fuente vigente, sin convertirse en fuente normativa del modo.

### 5.3 Mode Selection Criteria

Mode Selection Criteria estructura el juicio humano documentado.

Dimensiones minimas:

- sensibilidad de datos;
- exposicion a produccion;
- obligaciones de cumplimiento;
- criticidad de integraciones;
- impacto operacional;
- complejidad tecnica/conceptual;
- numero y criticidad de stakeholders;
- reversibilidad del cambio;
- vida esperada del proyecto;
- auditabilidad requerida;
- madurez del contexto disponible.

Reglas:

- cualquier dimension critica o no mitigada obliga a valorar `SDD Full`;
- riesgo controlado con alcance real de producto orienta a `SDD Lite`;
- solo bajo riesgo, baja exposicion, alta reversibilidad y ausencia de controles criticos permite `SDD Minimal`;
- no se usa scoring automatico.

### 5.4 Mode Lifecycle Rules

Mode Lifecycle Rules gobierna declaracion, reevaluacion, escalado y reduccion.

Incluye `Undeclared` como estado temporal para proyectos sin modo declarado. `Undeclared` no es un cuarto modo y no permite downgrade. Hasta declaracion aprobada, aplica baseline conservador equivalente a `SDD Full` para decisiones de fase, cambios de alcance, riesgos criticos, gates y readiness.

Quedan abiertos para Specification/Documentation posterior:

- quien aprueba modo inicial;
- quien aprueba cambios de modo;
- cadencia de reevaluacion si no hay eventos de riesgo;
- senales especificas adicionales que obligan a valorar Full.

### 5.5 Artifact Applicability Matrix

Artifact Applicability Matrix debe clasificar artefactos por modo como:

- obligatorio;
- condicional;
- recomendado;
- opcional;
- no habitual.

Debe evitar plantillas duplicadas por modo salvo decision posterior explicita. La matriz debe respetar que `Project Brief` contiene la declaracion inicial y que `docs/context_refs.md` funciona como indice de fuentes.

### 5.6 Agent Intervention Matrix

Agent Intervention Matrix mantiene un unico catalogo de agentes metodologicos.

Debe definir como adaptan su intervencion:

- Specification Agent;
- Architect Agent;
- Tasks Planner Agent;
- Reviewer Agent;
- Documentation Agent;
- QA Gate Agent;
- Implementation Agent;
- Legacy to SDD Agent para proyectos existentes.

No se crean variantes Minimal/Lite/Full de agentes.

### 5.7 Checks and Gates Policy

Checks and Gates Policy define la frontera entre checks ligeros y gates formales.

Reglas:

- checks ligeros se registran de forma consolidada en el artefacto de trabajo vigente del incremento o evidencia resumida;
- no se crea un archivo independiente por microtarea;
- cada check registra fecha o referencia temporal, alcance, criterio, resultado, responsable y referencia a evidencia cuando aplique;
- un check no autoriza cambio de fase ni sustituye aprobacion humana;
- un gate formal registra avance, bloqueo o readiness;
- riesgos criticos pueden elevar un check a gate en cualquier modo;
- `SDD Full` conserva gates formales del baseline vigente.

### 5.8 Evidence Policy

Evidence Policy preserva trazabilidad sin convertir documentos canonicos en historiales exhaustivos.

Reglas:

- la evidencia se consolida en artefacto de trabajo, decision, hito o gate;
- el historial Git puede aportar detalle tecnico o cronologico si queda referenciado;
- Git no sustituye decisiones normativas, justificaciones de modo, gates, riesgos criticos ni aprobaciones humanas;
- `docs/context_refs.md` no es repositorio de evidencias.

### 5.9 Compatibility Policy

Compatibility Policy evita romper repositorios derivados existentes.

Reglas:

- repositorios sin modo declarado quedan `Undeclared`;
- `Undeclared` no es un cuarto modo;
- no hay migracion automatica obligatoria;
- cambios significativos requieren declaracion de modo o decision explicita de mantener `Undeclared` con justificacion;
- ausencia de modo no reduce gobierno silenciosamente.

### 5.10 Validation Scenarios

Validation Scenarios se organiza en cuatro escenarios iniciales:

- VAL-001: experimento o utilidad interna de bajo riesgo, candidato a `SDD Minimal`;
- VAL-002: MVP o primera version con exposicion limitada, candidato a `SDD Lite`;
- VAL-003: proyecto productivo, sensible, regulado o con integraciones criticas, candidato a `SDD Full`;
- VAL-004: repositorio derivado existente sin `SDD Mode` declarado, para validar `Undeclared` y compatibilidad hacia atras.

Los repositorios concretos permanecen `PENDING` hasta que existan fuentes verificables antes de T-018.

---

## 6. Relationships and Interfaces

### 6.1 Documentary Flow

```text
docs/project_brief.md
        ↓
specs/spec-001-sdd-modes.md
        ↓
specs/spec-001-sdd-modes.architecture.md
        ↓
docs/tasks.md
        ↓
future documentation updates / reviews / gates, when authorized
```

### 6.2 Context Interface

`docs/context_refs.md` permanece como indice oficial de contexto.

Debe apuntar a la fuente vigente de declaracion de modo, fuentes externas pendientes y escenarios de validacion, pero no debe contener la policy completa ni evidencia exhaustiva.

### 6.3 Agent Interface

Los agentes consumen el modo declarado como contexto metodologico.

No se convierten en agentes separados por modo.

El mecanismo exacto por el que cada agente recibe el modo sigue abierto para tareas documentales posteriores.

### 6.4 Gate Interface

Los gates permanecen como controles formales de fase o readiness.

Checks ligeros pueden consolidarse por incremento gobernado, hito o evidencia resumida.

Condiciones criticas pueden elevar un check a gate con independencia del modo.

### 6.5 Template Interface

Las plantillas deben adaptarse solo cuando necesiten expresar campos o restricciones de modo.

No se introducen plantillas nuevas por defecto.

---

## 7. Dependencies

- `docs/project_brief.md`
- `docs/context_refs.md`
- `docs/tasks.md`
- `specs/spec-001-sdd-modes.md`
- `.github/instructions/sdd.instructions.md`
- `AGENTS.md`
- `README.md`
- `docs/glosario_terminos.md`
- future Reviewer Agent review of this architecture
- future Documentation Agent work after review

Pending external dependencies:

- URI and version of Professional OS note `[SDD] - SDD Modes`: `PENDING - discovery-only`
- URI and version of the conceptual consensus document about SDD Modes: `PENDING - discovery-only`
- concrete derived repositories for VAL-001 to VAL-004: `PENDING`

---

## 8. Alternatives Considered

### Alternative A - Mode Declaration in Project Brief

Status: Selected as canonical initial declaration source by `SPEC-001`.

Rationale:

- high precedence;
- visible at project start;
- aligned with initial context and scope.

Trade-offs:

- later mode changes should not overload Project Brief;
- subsequent changes must be recorded in the approved decision/gate artifact.

### Alternative B - Mode Declaration in Context References

Status: Not selected as normative source.

Rationale:

- `docs/context_refs.md` must remain an index and context-routing artifact;
- it may point to the current source of mode declaration but must not become policy.

### Alternative C - Mode Declaration in Dedicated Governance Section or Artifact

Status: Reserved for later lifecycle changes if needed.

Rationale:

- can support mode changes or governance decisions after initial Project Brief;
- must be approved explicitly to avoid unnecessary artifact growth.

### Alternative D - Mode Declaration in Specification or Frontmatter

Status: Optional subordinate metadata only if future decision defines precedence.

Rationale:

- useful for capability-level visibility;
- cannot override the project-level declaration without explicit precedence rules.

---

## 9. Architectural Decisions

### AD-001 - Keep SDD Modes inside the SDD Harness

Decision: SDD Modes is a documentary governance extension of the SDD Harness.

Rationale: The Foundation is explicitly not runtime, not an execution framework, and not a business logic repository.

### AD-002 - Preserve one methodological agent catalog

Decision: Existing agents adapt by mode; no per-mode agent variants are created.

Rationale: `SPEC-001` excludes duplicated agents for Minimal, Lite, and Full.

### AD-003 - Treat external pending sources as discovery-only

Decision: Professional OS and the conceptual consensus document remain non-normative discovery sources until URI and version are verified.

Rationale: `docs/context_refs.md` marks those sources as `PENDING - discovery-only`.

### AD-004 - Use matrix-based documentary structure

Decision: SDD Modes should be organized through matrices and policies rather than duplicated documents per mode.

Rationale: This supports proportionality while reducing duplication risk.

### AD-005 - Use Project Brief as canonical initial Mode Declaration source

Decision: The initial `SDD Mode` declaration belongs in `Project Brief`.

Rationale: This reflects the human decision in `SPEC-001` and avoids using `docs/context_refs.md` as normative policy.

### AD-006 - Treat `Undeclared` as compatibility state

Decision: `Undeclared` is a temporary compatibility state, not a fourth mode.

Rationale: Existing repositories must not be silently downgraded and do not require automatic migration.

### AD-007 - Use `incremento gobernado` as normative work unit

Decision: Tasks, checks, gates and evidence should refer to incrementos gobernados.

Rationale: The concept works before Development and avoids implementation-premature terminology. `Implementation Wave` remains optional inside Development.

---

## 10. Risks

| Risk | Impact | Mitigation |
| --- | --- | --- |
| Architecture accidentally becomes technical design | High | Keep all components documentary and defer implementation. |
| Mode rules duplicate across documents | Medium | Use `SPEC-001` as normative definition and other artifacts as operational summaries. |
| Project Brief becomes too operational | Medium | Initial declaration lives there; later changes move to approved decision/gate artifacts. |
| `docs/context_refs.md` becomes policy | Medium | Keep it as index and context route only. |
| Lite weakens critical controls | High | Critical controls remain mode-independent and can trigger gates. |
| Existing projects are silently downgraded | High | `Undeclared` applies conservative Full-equivalent baseline until declaration. |
| New templates proliferate | Medium | Prefer adapting existing templates unless a distinct purpose is proven. |
| Validation lacks real repositories | Medium | Keep concrete repos `PENDING` until T-018 has verifiable sources. |

---

## 11. Impact on Existing Architecture

`jqf-sdd-foundation` currently has a documentary SDD Harness with agents, instructions, templates, gates, eval structure and context governance.

SDD Modes impacts the existing architecture conceptually by adding proportional governance rules across existing documentary surfaces.

Likely affected areas for future authorized work:

- Project Brief template;
- SDD instructions;
- Specification template;
- context references guidance;
- agent instructions and Codex adapters;
- gates/checks guidance;
- glosario terminology;
- README high-level explanation.

This architecture does not modify those artifacts.

---

## 12. Open Architectural Questions

- How should each methodological agent receive or load the declared `SDD Mode` during its work?
- Should adaptation rules live primarily in common SDD instructions or in each agent instruction?
- Should mode appear as subordinate metadata in README, specification frontmatter, or both?
- Which existing templates can absorb mode fields without creating new templates?
- Which concrete repositories will instantiate VAL-001 to VAL-004?

---

## 13. Next Recommended Step

```text
QA Gate Agent execute T-018.
```

T-013 to T-016 have been completed and T-017 produced `PASS WITH CONDITIONS`. The documented conditions must remain corrected before validation or any readiness gate.

---

## Definition of Done

This architecture is ready when:

- the main documentary components are identified;
- responsibilities are clearly separated;
- relationships between Project Brief, Specification, Architecture, agents, checks, gates and templates are described;
- decisions from `SPEC-001` are reflected without being expanded by inference;
- no runtime, code, executable workflow, tool, integration or business logic is introduced;
- there is enough structure for documentation updates and later review.