# Architecture

## Metadatos

### Architecture ID

ARCH-001

### Spec relacionada

SPEC-001 - Consolidation Agent

### Title

Consolidation Agent Documentary Architecture

### Estado

Architecture

### Responsable

Jordi Quiroga

### Ultima actualizacion

2026-08-01

### Template

No existe una plantilla oficial de arquitectura To-Be en este repositorio. Este artefacto usa una estructura inferida a partir de `.github/agents/architect.agent.md` y permanece en alcance conceptual/documental.

---

## 1. Solution Summary

`Consolidation Agent` define la arquitectura documental del futuro agente metodologico encargado de preparar y reportar consolidaciones de capacidades SDD.

La solucion no crea el agente real, no crea definicion canonica en `.github/agents/`, no crea adaptador Codex, no crea runtime, scripts, tools, workflows ejecutables, automatizaciones, consolidaciones reales ni reorganizacion fisica. Define componentes conceptuales, responsabilidades, interfaces, decisiones, alternativas y restricciones necesarias para una futura creacion controlada del agente.

---

## 2. Architectural Objective

Definir una arquitectura comprensible para que el futuro `Consolidation Agent` pueda, cuando una fase posterior lo autorice:

- cargar contexto de una capacidad candidata a consolidacion;
- validar precondiciones documentales;
- clasificar artefactos por funcion y vigencia;
- proponer inventario canonico;
- proponer actualizaciones de indices;
- registrar deuda residual y puntos de reentrada;
- preparar handover final;
- reportar bloqueos y condiciones;
- integrarse con Reviewer Agent, Documentation Agent, QA Gate Agent y responsable humano sin sustituirlos.

---

## 3. Specification Decisions Reflected

| Specification decision | Architectural reflection |
| --- | --- |
| El agente es metodologico y no operativo de negocio | Se define como `Methodological Agent Boundary`, sin runtime ni herramientas reales. |
| El agente no aprueba ni sustituye QA/review | Se separan las recomendaciones documentales del componente `Review and Gate Handoff`. |
| Entradas minimas documentales | Se define `Input Context Loader` con artefactos obligatorios y condicionales. |
| Salidas no ejecutables | Se definen builders documentales de handover, indices, deuda y propuestas; ninguno ejecuta acciones. |
| Deuda residual visible | Se define `Residual Debt and Re-entry Mapper`. |
| Reorganizacion fisica solo propuesta | Se define `Physical Reorganization Proposal Builder` como `proposal-only`. |
| Errores recuperables | Se define `Recoverable Error Classifier`. |
| No crear agente real en esta fase | Toda la arquitectura permanece conceptual/documental. |

---

## 4. Main Components

| Componente | Responsabilidad | Estado |
| --- | --- | --- |
| Methodological Agent Boundary | Delimitar que el agente prepara y reporta, pero no aprueba ni ejecuta. | Definido conceptualmente. |
| Input Context Loader | Cargar Project Brief, SPEC, ARCH, Tasks, Readiness, Gates, handovers e indices. | Propuesto documentalmente. |
| Precondition Validator | Verificar artefactos minimos, fase, modo SDD, gates y autorizaciones. | Propuesto documentalmente. |
| Artifact Classification Engine | Clasificar artefactos por baseline, expediente, evidencia, deuda, reentrada o sustitucion. | Propuesto documentalmente. |
| Canonical Inventory Builder | Proponer baseline canonico minimo y reglas de carga futura. | Propuesto documentalmente. |
| Residual Debt and Re-entry Mapper | Registrar deuda residual, condiciones, owners y puntos de reentrada. | Propuesto documentalmente. |
| Handover Draft Builder | Preparar handover final de cierre como borrador revisable. | Propuesto documentalmente. |
| Index Update Proposal Builder | Proponer cambios a indices y context refs sin aplicarlos automaticamente. | Propuesto documentalmente. |
| Physical Reorganization Proposal Builder | Formular reorganizacion fisica como propuesta no ejecutable. | Propuesto documentalmente. |
| Recoverable Error Classifier | Convertir errores recuperables en bloqueos, condiciones o reentradas. | Propuesto documentalmente. |
| Review and Gate Handoff | Entregar paquete a Reviewer Agent, QA Gate Agent y responsable humano. | Propuesto documentalmente. |

---

## 5. Component Responsibilities

### 5.1 Methodological Agent Boundary

Define los limites del futuro agente.

Debe garantizar que el agente:

- no aprueba Specification;
- no aprueba Architecture;
- no emite QA Gate final;
- no sustituye aprobacion humana;
- no autoriza Development;
- no crea runtime ni tools;
- no mueve ni elimina archivos;
- no modifica normativa por iniciativa propia.

### 5.2 Input Context Loader

Carga y normaliza referencias a artefactos fuente.

Entradas esperadas:

- Project Brief;
- Context References;
- SPEC;
- ARCH si existe;
- Tasks;
- Readiness;
- QA Gates;
- Closure Handover si existe;
- Evidence Index si existe;
- Residual Debt Register si existe;
- indices de capacidades cuando existan.

Debe conservar la distincion entre inputs obligatorios, condicionales y discovery-only.

### 5.3 Precondition Validator

Verifica si una capacidad puede preparar consolidacion.

Checks minimos:

- fase actual identificada;
- `SDD Mode` declarado o tratado como `Undeclared` conservador;
- SPEC existente;
- Tasks existente;
- Readiness existente;
- gates requeridos presentes o ausencia marcada como bloqueo;
- Reviewer/QA/human decisions presentes cuando apliquen;
- ausencia de implementacion prematura;
- restricciones de baselines cerrados respetadas.

Resultado permitido:

- `Eligible`;
- `Eligible with conditions`;
- `Blocked`.

### 5.4 Artifact Classification Engine

Clasifica artefactos segun su funcion posterior al cierre.

Categorias minimas:

- `canonical-baseline`;
- `closed-methodological-dossier`;
- `historical-evidence`;
- `superseded-artifact`;
- `residual-debt`;
- `re-entry-point`;
- `proposal-only`.

Cada clasificacion debe incluir motivo, fuente y restricciones de uso futuro.

### 5.5 Canonical Inventory Builder

Construye una propuesta de inventario canonico minimo.

Debe responder:

- que artefactos futuras capacidades deben cargar por defecto;
- que artefactos quedan solo para auditoria o reentrada;
- que artefactos quedan sustituidos;
- que referencias deben conservarse para trazabilidad.

No puede reclasificar por si mismo un baseline cerrado; solo puede proponerlo.

### 5.6 Residual Debt and Re-entry Mapper

Registra deuda residual y puntos de reentrada.

Campos minimos para deuda:

- ID;
- descripcion;
- tipo;
- estado;
- impacto;
- owner;
- bloquea avance;
- evidencia requerida para cierre;
- punto de reentrada.

Campos minimos para reentrada:

- condicion de activacion;
- agente recomendado;
- artefactos minimos a cargar;
- evidencia minima;
- fase SDD esperada;
- restricciones vigentes.

### 5.7 Handover Draft Builder

Prepara un borrador de handover final.

Debe incluir:

- estado final propuesto;
- modo SDD aplicado;
- baseline canonico propuesto;
- expediente historico disponible;
- decisiones finales encontradas;
- gates y aprobaciones;
- deuda residual;
- puntos de reentrada;
- riesgos residuales;
- autorizaciones no concedidas;
- siguiente accion valida.

El handover producido queda sujeto a review, QA Gate y decision humana.

### 5.8 Index Update Proposal Builder

Produce una lista de actualizaciones propuestas para:

- `docs/capabilities/index.md`;
- `specs/capabilities/index.md`;
- context refs de la capacidad;
- evidence index;
- residual debt register;
- closure handover.

No aplica cambios automaticamente salvo que una fase futura y agente responsable lo autoricen explicitamente.

### 5.9 Physical Reorganization Proposal Builder

Describe cambios fisicos recomendados solo como `proposal-only`.

Cada propuesta debe indicar:

- archivos o familias afectadas;
- motivo;
- riesgo;
- precondiciones;
- capacidad futura requerida;
- aprobacion humana necesaria;
- evidencia minima para ejecutar.

No puede mover, renombrar, eliminar ni reescribir archivos.

### 5.10 Recoverable Error Classifier

Convierte errores recuperables en salidas gobernadas.

Estados permitidos:

- `Blocked`;
- `Condition`;
- `Re-entry required`;
- `Needs human decision`;
- `Needs Reviewer Agent`;
- `Needs QA Gate Agent`;
- `Needs Documentation Agent`.

### 5.11 Review and Gate Handoff

Entrega el paquete resultante a los agentes responsables.

Routing esperado:

- Reviewer Agent para coherencia y contradicciones;
- Documentation Agent para actualizaciones documentales autorizadas;
- QA Gate Agent para readiness, Consolidation Readiness Gate o Closure Gate;
- responsable humano para aprobaciones y cambios de baseline;
- Architect Agent para reorganizacion fisica futura o cambios de estructura;
- Implementation Agent solo si una fase futura autoriza Development.

---

## 6. Relationships and Interfaces

### 6.1 Conceptual Agent Flow

```text
Capability candidate
  -> Input Context Loader
  -> Precondition Validator
  -> Artifact Classification Engine
  -> Canonical Inventory Builder
  -> Residual Debt and Re-entry Mapper
  -> Handover Draft Builder
  -> Index Update Proposal Builder
  -> Review and Gate Handoff
```

### 6.2 Blocked Flow

```text
Missing or contradictory input
  -> Recoverable Error Classifier
  -> Blocked / Condition / Re-entry required
  -> Recommended agent or human decision
```

### 6.3 Physical Reorganization Flow

```text
Physical normalization need detected
  -> Physical Reorganization Proposal Builder
  -> proposal-only report
  -> future authorized capability
```

### 6.4 Review and Gate Interface

The future agent may produce a consolidation package, but the package cannot advance without:

1. Reviewer Agent review when coherence or contradiction risk exists.
2. QA Gate Agent decision for applicable gates.
3. Human approval when closing, changing baseline, resolving debt ownership or authorizing physical changes.

### 6.5 Documentation Interface

Documentation Agent may consume proposed updates and apply them only when:

- the task is authorized;
- phase constraints permit it;
- closed baselines are not modified without approval;
- changes remain documentary and non-executable.

---

## 7. Proposed Documentary Output Structure

A future `Consolidation Agent` report should be documentable as a single package or as sections inside handover/readiness artifacts.

Minimum structure:

```text
Consolidation Agent Report
  1. Input set reviewed
  2. Precondition result
  3. Artifact classification
  4. Canonical inventory proposal
  5. Residual debt register proposal
  6. Re-entry point register proposal
  7. Handover draft
  8. Index update proposal
  9. Physical reorganization proposal, if any
  10. Blockers and conditions
  11. Required review/gate/human decisions
```

This architecture does not create a report template yet. A future Documentation phase may decide whether the report is a standalone template or a section in existing closure artifacts.

---

## 8. Dependencies

- `docs/capabilities/consolidation-agent/project_brief.md`
- `docs/capabilities/consolidation-agent/context_refs.md`
- `docs/capabilities/consolidation-agent/tasks.md`
- `docs/capabilities/consolidation-agent/sdd_readiness_assessment.md`
- `specs/capabilities/consolidation-agent/spec-001-consolidation-agent.md`
- `specs/capabilities/project-consolidation-and-closure/spec-001-sdd-project-consolidation-and-closure.md`
- `specs/capabilities/project-consolidation-and-closure/arch-001-sdd-project-consolidation-and-closure.md`
- `docs/capabilities/project-consolidation-and-closure/closure_handover.md`
- `docs/capabilities/project-consolidation-and-closure/evidence_index.md`
- `docs/capabilities/project-consolidation-and-closure/residual_debt.md`
- `.github/instructions/sdd.instructions.md`
- `AGENTS.md`
- `.github/agents/architect.agent.md`

---

## 9. Restrictions

- No implementar runtime.
- No crear scripts, tools ni workflows ejecutables.
- No crear automatizaciones.
- No crear definicion canonica del agente en `.github/agents/`.
- No crear adaptador Codex en `.codex/agents/`.
- No crear el `Consolidation Agent` real.
- No ejecutar consolidaciones reales.
- No mover, renombrar ni eliminar artefactos.
- No modificar baselines cerrados.
- No autorizar Development.
- No sustituir Reviewer Agent, QA Gate Agent ni aprobacion humana.

---

## 10. Alternatives Considered

### Alternative A - Single monolithic agent step

Estado: Rechazada.

Pros:

- mas simple de describir;
- menor numero de componentes conceptuales.

Cons:

- mezcla validacion, clasificacion, deuda, handover y routing;
- dificulta auditar responsabilidades;
- aumenta riesgo de que recomendaciones parezcan aprobaciones.

### Alternative B - Componentized documentary pipeline

Estado: Seleccionada.

Pros:

- separa responsabilidades;
- mantiene trazabilidad;
- facilita review y QA;
- permite aplicar solo partes del agente en fases futuras;
- reduce riesgo de ejecucion prematura.

Cons:

- requiere disciplina de naming y reporte;
- puede parecer mas amplio de lo necesario si no se mantiene documental.

### Alternative C - Embed behavior only in AGENTS.md

Estado: Rechazada para esta fase.

Pros:

- acercaria la definicion al catalogo de agentes;
- facilitaria futura incorporacion.

Cons:

- podria presentar el agente como vigente;
- contradice la restriccion de no crear el agente real todavia;
- reduce trazabilidad de la capacidad SDD.

### Alternative D - Implement checks as scripts first

Estado: Rechazada.

Pros:

- permitiria validacion repetible.

Cons:

- es Development/tooling;
- no esta autorizado;
- podria desplazar decision humana por automatizacion prematura.

---

## 11. Architectural Decisions

### AD-001 - Use a componentized documentary pipeline

Decision: El comportamiento futuro del agente se modela como pipeline documental por componentes.

Razonamiento: Separa responsabilidades y evita que una recomendacion se confunda con aprobacion.

### AD-002 - Keep all outputs non-executable

Decision: Todas las salidas se consideran propuestas, borradores o reportes documentales.

Razonamiento: La specification prohibe ejecucion, reorganizacion fisica y autorizacion de Development.

### AD-003 - Put debt and re-entry in a dedicated component

Decision: Deuda residual y reentrada se gestionan juntas en `Residual Debt and Re-entry Mapper`.

Razonamiento: Toda deuda debe tener punto de reentrada; separarlas aumenta riesgo de perdida de trazabilidad.

### AD-004 - Make physical reorganization proposal-only

Decision: La reorganizacion fisica se aisla en un componente que solo emite propuestas.

Razonamiento: Cualquier movimiento requiere capacidad futura autorizada.

### AD-005 - Route decisions outward

Decision: Review, gate y aprobacion humana quedan fuera del agente.

Razonamiento: Mantiene los limites del SDD Harness y evita sustitucion de agentes existentes.

### AD-006 - Do not update AGENTS.md or agent adapters now

Decision: Esta arquitectura no incorpora `Consolidation Agent` al catalogo vigente ni a Codex.

Razonamiento: Crear el agente real requiere fase/capacidad posterior autorizada.

---

## 12. Risks

| Riesgo | Impacto | Mitigacion |
| --- | --- | --- |
| La arquitectura se interprete como permiso para crear el agente | Alto | Repetir que es conceptual y no actualiza AGENTS ni adapters. |
| El pipeline parezca automatizacion ejecutable | Alto | Definir todos los componentes como documentales y no ejecutables. |
| La recomendacion del agente se confunda con QA Gate | Alto | `Review and Gate Handoff` separa decision de propuesta. |
| La deuda residual se duplique o fragmente | Medio | Unificar deuda y reentrada en un componente. |
| La propuesta de indices se aplique sin autorizacion | Medio | Marcar `Index Update Proposal Builder` como propuesta. |
| La reorganizacion fisica se ejecute prematuramente | Alto | Mantener `proposal-only` y capacidad futura requerida. |

---

## 13. Impact on Existing Architecture

Impactos de esta Architecture:

- `docs/capabilities/consolidation-agent/tasks.md`: debe registrar autorizacion de Architecture y creacion de `ARCH-001`.
- `docs/capabilities/consolidation-agent/sdd_readiness_assessment.md`: registra fase actual `Architecture`, review T-010 y QA Gate T-011.
- `docs/capabilities/consolidation-agent/context_refs.md`: indexa `ARCH-001`, autorizacion humana, review y QA Gate de Architecture.
- `docs/capabilities/index.md`: debe incluir `ARCH-001` como spec principal de la capacidad.
- `specs/capabilities/index.md`: debe indexar `ARCH-001`.
- `AGENTS.md`, `.github/agents/` y `.codex/agents/`: sin cambios en esta fase.
- Baselines cerrados: sin cambios.

---

## 14. Open Architectural Questions

- El futuro reporte del agente sera un artefacto propio o una seccion de `closure_handover.md`?
- Que formato exacto tendra la tabla de clasificacion de artefactos?
- Debe existir un template de `consolidation_agent_report.md`?
- Que nivel de automatizacion futura sera aceptable sin sustituir QA Gate?
- Que evidencia minima debe adjuntar una propuesta de reorganizacion fisica?
- Cuando se cree el agente real, se incorporara primero en `.github/agents/` o junto con adaptador Codex?

---

## 15. Next Recommended Step

```text
Decision humana sobre la siguiente fase documental tras QA Gate de Architecture.
```

Reviewer Agent emitio `Approved with minor corrections` y QA Gate Agent emitio `Pass with minor conditions`. El siguiente paso requiere decision humana sobre la siguiente fase documental.

Development permanece `NOT AUTHORIZED`.

---

## Definition of Done

Esta arquitectura esta lista cuando:

- los componentes principales estan identificados;
- las responsabilidades estan claramente definidas;
- las interfaces documentales estan descritas;
- las dependencias y restricciones estan documentadas;
- las alternativas y decisiones arquitectonicas estan justificadas;
- el impacto sobre la arquitectura existente esta identificado;
- no se introduce implementacion, runtime, agente real, workflow ejecutable ni reorganizacion fisica.