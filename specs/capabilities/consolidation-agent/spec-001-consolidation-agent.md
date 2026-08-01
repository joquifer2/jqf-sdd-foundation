# Specification

## Metadatos

### Spec ID

SPEC-001

### Title

Consolidation Agent

### Estado

Specification

### Responsable

Jordi Quiroga

### Ultima actualizacion

2026-08-01

---

### SDD Mode Reference

Modo declarado para el proyecto o capacidad:

`SDD Full`

Justificacion o referencia canonica:

`docs/capabilities/consolidation-agent/project_brief.md`

Notas:

- Esta specification no autoriza Development.
- Esta specification no crea el `Consolidation Agent` real.
- Esta specification no crea definicion canonica en `.github/agents/` ni adaptador en `.codex/agents/`.
- Esta specification no ejecuta consolidaciones reales ni reorganizacion fisica.

---

## 1. Purpose

Definir el comportamiento metodologico del futuro `Consolidation Agent`, responsable de preparar y reportar documentalmente el proceso de consolidacion definido por `SDD Project Consolidation and Closure`.

El agente debe ayudar a clasificar artefactos, proponer baseline canonico, registrar deuda residual, identificar puntos de reentrada, preparar handover final y proponer reorganizacion fisica sin ejecutarla.

---

## 2. Background

La Foundation ya dispone de capacidades cerradas que establecen baseline metodologico:

- `SDD Modes`;
- `SDD Project Consolidation and Closure`;
- `Foundation Derivation and Project Initialization`.

`SDD Project Consolidation and Closure` definio la fase `Consolidation`, el estado `Closed`, los tipos documentales de cierre y la interfaz conceptual de un futuro agente. Esta specification convierte esa interfaz conceptual en definicion de comportamiento verificable, sin crear todavia el agente real.

---

## 3. Objective

La capacidad debe producir una specification completa del `Consolidation Agent` que permita responder:

- que proposito tiene;
- que responsabilidades asume;
- donde estan sus limites;
- que entradas consume;
- que salidas produce;
- que flujo operativo sigue;
- que decisiones puede proponer;
- que decisiones no puede tomar;
- como interactua con otros agentes y con aprobacion humana;
- como gestiona errores recuperables y reentradas.

---

## 4. Scope

### Included

- Definicion de proposito, responsabilidades, limites y principios de actuacion.
- Definicion de entradas minimas: Project Brief, SPEC, ARCH, Tasks, Readiness, QA Gates, Closure Handover e indices de capacidades.
- Definicion de salidas minimas: clasificacion de artefactos, inventario canonico, actualizacion propuesta de indices, registro de deuda residual, registro de puntos de reentrada, handover final y propuesta de reorganizacion fisica.
- Definicion de flujo operativo.
- Definicion de decisiones permitidas y prohibidas.
- Definicion de integracion con Specification, Architect, Tasks Planner, Reviewer, Documentation, QA Gate, Implementation y responsable humano.
- Definicion de errores recuperables y puntos de reentrada.
- Criterios de aceptacion verificables para la specification.

### Excluded

- Implementar el agente.
- Crear scripts, tools, workflows ejecutables, prompts operativos o automatizaciones.
- Crear o modificar `.github/agents/` o `.codex/agents/`.
- Aprobar Specification, Architecture, QA Gates, Consolidation o Closed.
- Modificar normativa aprobada.
- Modificar baseline cerrado de capacidades previas.
- Ejecutar despliegues.
- Eliminar historia Git.
- Reorganizar fisicamente el repositorio.
- Ejecutar consolidaciones reales.

---

## 5. Actors

| Actor | Descripcion |
| --- | --- |
| Responsable humano | Aprueba decisiones relevantes, cierre, cambios de baseline y reorganizacion fisica. |
| Consolidation Agent | Futuro agente metodologico que prepara y reporta consolidaciones documentales. |
| Specification Agent | Define o revisa specifications; no es sustituido por Consolidation Agent. |
| Architect Agent | Define estructuras conceptuales; recibe hallazgos de consolidacion como input futuro. |
| Tasks Planner Agent | Convierte trabajo autorizado en tareas trazables. |
| Reviewer Agent | Revisa coherencia, alcance, contradicciones y calidad documental. |
| Documentation Agent | Aplica actualizaciones documentales autorizadas, indices y handovers. |
| QA Gate Agent | Evalua gates, readiness y criterios de avance. |
| Implementation Agent | Solo interviene en Development autorizado; Consolidation Agent no lo activa por si mismo. |
| GitHub Workflow Agent | Mantiene trazabilidad con issues o repositorio cuando una fase futura lo autorice. |

---

## 6. Inputs

| Input | Descripcion | Obligatorio |
| --- | --- | --- |
| Project Brief | Fuente de alcance, modo SDD, restricciones, riesgos y decision humana inicial. | Si |
| SPEC | Specification final o candidata de la capacidad a consolidar. | Si |
| ARCH | Architecture final o candidata, si la capacidad llego a Architecture. | Condicional |
| Tasks | Backlog con tareas completadas, descartadas, pendientes, decisiones y condiciones. | Si |
| Readiness | Assessment vigente y evidencias de preparacion por fase. | Si |
| QA Gates | Decisiones de gates aplicables, condiciones y bloqueos. | Si |
| Closure Handover | Handover existente si la capacidad ya tiene intento previo de cierre o reentrada. | Condicional |
| Indices de capacidades | `docs/capabilities/index.md` y `specs/capabilities/index.md` cuando existan. | Si existen |
| Context References | Indice de fuentes, jerarquia, contexto pendiente y fuentes discovery-only. | Si |
| Evidence Index | Indice de evidencia historica cuando exista. | Condicional |
| Residual Debt Register | Registro de deuda residual cuando exista o deba crearse. | Condicional |
| Aprobacion humana | Decision explicita para iniciar o completar cierre, si aplica transicion de estado. | Si para cierre |

---

## 7. Outputs

| Output | Descripcion | Ejecutable |
| --- | --- | --- |
| Clasificacion de artefactos | Tabla que clasifica cada artefacto como baseline canonico, expediente historico, evidencia, sustituido, deuda o reentrada. | No |
| Inventario canonico | Propuesta de artefactos vigentes que futuras capacidades deberian cargar por defecto. | No |
| Actualizacion propuesta de indices | Cambios sugeridos para indices de capacidades, specs, evidencia o contexto. | No |
| Registro de deuda residual | Deudas restantes con ID, tipo, estado, impacto, owner, bloqueo y punto de reentrada. | No |
| Registro de puntos de reentrada | Condiciones, agente recomendado, artefactos a cargar y evidencia minima para retomar deuda o decisiones. | No |
| Handover final | Resumen de cierre, decisiones, gates, condiciones, riesgos, baseline y autorizaciones no concedidas. | No |
| Propuesta de reorganizacion fisica | Recomendacion de movimientos o normalizacion fisica, marcada como `proposal-only`. | No |
| Reporte de bloqueos | Lista de inconsistencias, missing inputs, contradicciones o condiciones que impiden consolidar. | No |

Ninguna salida ejecuta cambios por si misma. Las salidas son propuestas o artefactos documentales sujetos a review, gate o decision humana segun corresponda.

---

## 8. Responsibilities

### R-001 - Verificacion de precondiciones

El agente debe verificar que existen artefactos minimos, modo SDD, fase actual, gates aplicables y ausencia de implementacion prematura antes de preparar consolidacion.

### R-002 - Clasificacion documental

El agente debe clasificar artefactos en categorias compatibles con `SDD Project Consolidation and Closure`:

- baseline canonico;
- expediente metodologico cerrado;
- evidencia historica;
- artefactos sustituidos;
- deuda residual;
- puntos de reentrada;
- proposal-only para reorganizacion fisica.

### R-003 - Preservacion de deuda

El agente debe registrar deuda residual visible. No puede cerrarla, ocultarla, fusionarla o descartarla sin decision documentada.

### R-004 - Preparacion de handover

El agente debe preparar un handover final comprensible sin obligar a cargar todo el expediente historico.

### R-005 - Reduccion controlada de contexto

El agente debe recomendar el contexto minimo que futuras capacidades deben cargar, preservando rutas de auditoria y reentrada.

### R-006 - Propuesta de actualizaciones

El agente puede proponer actualizaciones a indices y referencias. Solo puede aplicarlas si la fase, agente responsable y aprobacion aplicable lo autorizan.

### R-007 - Deteccion de contradicciones

El agente debe reportar contradicciones entre Project Brief, SPEC, ARCH, Tasks, Gates, Readiness e indices.

### R-008 - Preparacion de reentrada

El agente debe definir puntos de reentrada para deuda, decisiones diferidas, bloqueos, capacidades futuras y reorganizacion fisica.

---

## 9. Limits

El `Consolidation Agent` no puede:

- aprobar Specification;
- aprobar Architecture;
- sustituir Reviewer Agent;
- sustituir QA Gate Agent;
- sustituir aprobacion humana;
- modificar normativa;
- ocultar deuda;
- eliminar historia Git;
- ejecutar despliegues;
- crear runtime, scripts, tools o workflows ejecutables;
- modificar artefactos cerrados por iniciativa propia;
- reorganizar fisicamente el repositorio por iniciativa propia;
- declarar `Development AUTHORIZED`;
- convertir fuentes discovery-only en normativas sin decision explicita.

---

## 10. Operational Flow

### Step 1 - Load governance context

Leer Project Brief, context refs, SDD instructions, indices y handover previo si existe.

Resultado esperado: fase, modo SDD, alcance, restricciones y fuentes obligatorias identificadas.

### Step 2 - Validate required inputs

Comprobar presencia y estado de SPEC, ARCH si aplica, Tasks, Readiness, QA Gates e indices.

Resultado esperado: lista de inputs validos, faltantes o contradictorios.

### Step 3 - Check phase eligibility

Determinar si la capacidad puede entrar en `Consolidation` o si requiere review, QA, decision humana o correccion documental previa.

Resultado esperado: `Eligible`, `Eligible with conditions` o `Blocked`.

### Step 4 - Classify artifacts

Clasificar artefactos por funcion documental y vigencia.

Resultado esperado: clasificacion de artefactos con justificacion.

### Step 5 - Build canonical inventory

Proponer baseline canonico minimo y contexto futuro recomendado.

Resultado esperado: inventario canonico y reglas de carga futura.

### Step 6 - Register residual debt and re-entry

Crear o actualizar propuesta de deuda residual y puntos de reentrada.

Resultado esperado: deuda visible con owner, impacto, bloqueo y condicion de cierre.

### Step 7 - Prepare handover

Preparar handover final con estado, decisiones, gates, baseline, deuda, riesgos, reentradas y autorizaciones denegadas.

Resultado esperado: borrador de handover listo para review.

### Step 8 - Propose index updates

Proponer actualizaciones a indices de capacidades, specs y evidencias.

Resultado esperado: lista de cambios propuesta, no aplicada salvo autorizacion.

### Step 9 - Propose physical reorganization

Si procede, describir reorganizacion fisica recomendada como `proposal-only`.

Resultado esperado: propuesta no ejecutada, con precondiciones y capacidad futura requerida.

### Step 10 - Hand off to review and gate

Entregar paquete a Reviewer Agent y QA Gate Agent.

Resultado esperado: ningun cierre queda aprobado hasta review, gate y decision humana aplicable.

---

## 11. Allowed Decisions

El agente puede:

- declarar que un input esta presente, ausente, desactualizado o contradictorio;
- proponer clasificacion de artefactos;
- proponer inventario canonico;
- proponer actualizacion de indices;
- proponer registro de deuda residual;
- proponer puntos de reentrada;
- proponer handover final;
- recomendar `Blocked`, `Eligible` o `Eligible with conditions` para entrada a Consolidation;
- recomendar que intervenga Reviewer, Documentation, QA Gate, Architect, Tasks Planner o responsable humano;
- proponer reorganizacion fisica como `proposal-only`.

---

## 12. Prohibited Decisions

El agente no puede:

- aprobar una Specification;
- aprobar una Architecture;
- aprobar un QA Gate;
- declarar cierre final por si mismo;
- autorizar Development;
- modificar normativa o precedencia documental;
- cerrar deuda residual sin evidencia y decision;
- cambiar el estado de una capacidad cerrada sin aprobacion;
- ejecutar movimientos fisicos de archivos;
- eliminar o reescribir historia Git;
- ejecutar despliegues;
- decidir tecnologias, runtime o automatizaciones;
- convertir propuestas en cambios aplicados sin agente/fase autorizada.

---

## 13. Integration with Other Agents

| Agente | Integracion permitida | Limite |
| --- | --- | --- |
| Specification Agent | Recibe hallazgos de alcance, limites o contradicciones para corregir specs futuras. | Consolidation Agent no aprueba specs. |
| Architect Agent | Recibe propuestas de estructura, reorganizacion fisica o interfaces futuras. | Consolidation Agent no crea Architecture. |
| Tasks Planner Agent | Recibe trabajo pendiente convertido en backlog trazable. | Consolidation Agent no crea plan final si no esta autorizado. |
| Reviewer Agent | Revisa paquete de consolidacion, coherencia y riesgos. | Consolidation Agent no sustituye review. |
| Documentation Agent | Aplica actualizaciones documentales autorizadas. | Consolidation Agent no aplica cambios globales por iniciativa propia. |
| QA Gate Agent | Evalua Consolidation Readiness y Closure Gate. | Consolidation Agent no emite gate final. |
| Implementation Agent | Solo recibe input si Development esta autorizado por otros mecanismos. | Consolidation Agent no autoriza Development. |
| GitHub Workflow Agent | Puede recibir trazabilidad de issues/PRs si se autoriza. | Consolidation Agent no elimina ni reescribe historia Git. |

---

## 14. Recoverable Errors

| Error recuperable | Comportamiento requerido | Reentrada |
| --- | --- | --- |
| Input obligatorio ausente | Marcar `Blocked`, listar artefacto faltante y agente recomendado. | Volver tras crear o localizar el artefacto. |
| Estado inconsistente entre artefactos | Marcar contradiccion y precedencia afectada. | Reviewer Agent o Documentation Agent corrige. |
| QA Gate ausente | No consolidar; solicitar evaluacion por QA Gate Agent. | Reintentar con gate documentado. |
| Deuda residual sin owner | Marcar deuda incompleta y no cerrar. | Responsable humano asigna owner. |
| Reentrada no definida | Registrar missing re-entry como bloqueo o condicion. | Specification/Documentation completa punto de reentrada. |
| Indices desactualizados | Proponer actualizacion y marcar condicion. | Documentation Agent aplica si autorizado. |
| Propuesta de reorganizacion fisica necesaria | Marcar `proposal-only` y requerir capacidad futura. | Architect/QA/humano autorizan fase futura. |
| Fuente discovery-only usada como normativa | Bloquear o degradar a referencia no normativa. | Responsable humano decide si la eleva. |

---

## 15. Re-entry Points

El agente debe registrar puntos de reentrada para:

- deuda residual metodologica, empirica, tecnica, documental o de gobernanza;
- decisiones diferidas;
- artefactos faltantes;
- gates pendientes;
- reorganization proposals;
- capacidades futuras derivadas;
- contradicciones no resueltas;
- reactivacion de una capacidad `On Hold`, `Superseded`, `Archived` o `Cancelled`.

Cada punto de reentrada debe indicar:

- condicion de activacion;
- agente recomendado;
- artefactos minimos a cargar;
- evidencia requerida;
- fase SDD esperada;
- restricciones vigentes.

---

## 16. Functional Requirements

### FR-001

El agente debe validar que los inputs minimos existen antes de preparar consolidacion.

### FR-002

El agente debe clasificar artefactos por vigencia, funcion y estado.

### FR-003

El agente debe generar una propuesta de inventario canonico.

### FR-004

El agente debe registrar deuda residual visible y trazable.

### FR-005

El agente debe registrar puntos de reentrada para deuda, decisiones diferidas y bloqueos.

### FR-006

El agente debe preparar handover final o reportar por que no puede prepararlo.

### FR-007

El agente debe proponer actualizaciones de indices sin aplicarlas automaticamente.

### FR-008

El agente debe proponer reorganizacion fisica solo como `proposal-only`.

### FR-009

El agente debe detectar contradicciones entre artefactos y reportar precedencia.

### FR-010

El agente debe integrarse con Reviewer Agent y QA Gate Agent sin sustituirlos.

### FR-011

El agente debe preservar restricciones de `SDD Mode` y fase vigente.

### FR-012

El agente no debe autorizar Development ni ejecutar cambios tecnicos.

---

## 17. Business Rules

### BR-001

Una consolidacion no es valida si no existe evidencia suficiente de review, gate o decision humana aplicable.

### BR-002

Toda deuda residual debe quedar visible o el cierre debe bloquearse.

### BR-003

El baseline canonico debe ser minimo suficiente, no una copia del expediente completo.

### BR-004

El expediente historico debe permanecer discoverable para auditoria o reentrada.

### BR-005

Toda reorganizacion fisica requiere capacidad especifica autorizada.

### BR-006

El agente puede recomendar, pero no aprobar.

### BR-007

La ausencia de implementacion prematura es una condicion obligatoria.

---

## 18. Constraints

- Estado de esta specification: `Specification`; fase actual de la capacidad: `Architecture` documental tras autorizacion humana T-008.
- Architecture documental fue creada posteriormente mediante T-008/T-009; esta specification no autorizo Development ni agente real.
- No crear agente real.
- No crear scripts, tools ni workflows.
- No modificar normativa aprobada.
- No modificar baselines cerrados.
- No ejecutar consolidaciones reales.
- No ejecutar reorganizacion fisica.
- No eliminar historia Git.

---

## 19. Assumptions

- Las capacidades de baseline declaradas por la solicitud estan `Closed`.
- El agente futuro sera parte del SDD Harness, no del Operational Harness.
- La aprobacion humana seguira siendo necesaria para cierre y cambios de baseline.
- Los indices existentes son catalogos de routing y no specifications normativas.
- Las salidas del agente podran ser artefactos documentales o propuestas, no acciones ejecutadas.

---

## 20. Risks

| Riesgo | Impacto | Notas |
| --- | --- | --- |
| El agente se use para aprobar gates automaticamente | Alto | Debe integrarse con QA Gate sin sustituirlo. |
| La propuesta de reorganizacion se ejecute sin autorizacion | Alto | Debe marcarse como `proposal-only`. |
| Deuda residual se oculte en handover resumido | Alto | Debe tener registro explicito. |
| El inventario canonico pierda trazabilidad historica | Medio | Debe apuntar al expediente cerrado. |
| El agente duplique funciones de Documentation Agent | Medio | Solo propone o prepara, Documentation aplica cuando este autorizado. |
| La futura definicion canonica contradiga esta spec | Medio | Architecture/review posterior debe resolver la alineacion. |

---

## 21. Acceptance Criteria

### AC-001

La specification define proposito, responsabilidades y limites del `Consolidation Agent`.

### AC-002

La specification define entradas minimas, incluyendo Project Brief, SPEC, ARCH, Tasks, Readiness, QA Gates, Closure Handover e indices de capacidades.

### AC-003

La specification define salidas minimas, incluyendo clasificacion de artefactos, inventario canonico, actualizacion propuesta de indices, deuda residual, puntos de reentrada, handover final y propuesta de reorganizacion fisica sin ejecucion.

### AC-004

La specification define flujo operativo completo.

### AC-005

La specification distingue decisiones permitidas y decisiones prohibidas.

### AC-006

La specification define integracion con los demas agentes sin sustituir Reviewer, QA Gate ni aprobacion humana.

### AC-007

La specification define errores recuperables y puntos de reentrada.

### AC-008

La specification prohibe aprobar Specification, aprobar Architecture, modificar normativa, ocultar deuda, eliminar historia Git, desplegar, autorizar Development o reorganizar fisicamente el repositorio por iniciativa propia.

### AC-009

La specification permanece como artefacto de `Specification`; la capacidad puede avanzar documentalmente por gates posteriores sin crear implementacion.

---

## 22. Dependencies

- `docs/capabilities/consolidation-agent/project_brief.md`
- `docs/capabilities/consolidation-agent/context_refs.md`
- `docs/capabilities/consolidation-agent/sdd_readiness_assessment.md`
- `specs/capabilities/consolidation-agent/arch-001-consolidation-agent.md`
- `docs/capabilities/consolidation-agent/tasks.md`
- `specs/capabilities/project-consolidation-and-closure/spec-001-sdd-project-consolidation-and-closure.md`
- `specs/capabilities/project-consolidation-and-closure/arch-001-sdd-project-consolidation-and-closure.md`
- `docs/capabilities/project-consolidation-and-closure/closure_handover.md`
- `docs/capabilities/project-consolidation-and-closure/evidence_index.md`
- `docs/capabilities/project-consolidation-and-closure/residual_debt.md`
- `docs/capabilities/index.md`
- `specs/capabilities/index.md`
- `.github/instructions/sdd.instructions.md`
- `AGENTS.md`
- `.github/agents/specification.agent.md`

---

## 23. Open Questions

- Que estructura exacta tendra la futura definicion canonica del agente?
- Debe existir un template especifico de reporte del `Consolidation Agent`?
- Que parte de la propuesta de indices puede aplicar Documentation Agent sin nueva capacidad?
- Que gate autorizara crear el agente real?
- Como se representaran multiples intentos de consolidacion de una misma capacidad?

---

## 24. Future Considerations

- COMPLETADO 2026-08-01: `ARCH-001 - Consolidation Agent` creado tras autorizacion humana, revisado y validado por QA Gate T-011.
- Crear definicion canonica en `.github/agents/` solo en fase posterior autorizada.
- Crear adaptador Codex en `.codex/agents/` solo despues de definicion canonica.
- Definir template de reporte del agente.
- Evaluar automatizaciones no ejecutables primero y tools reales solo en Development autorizado.
- Evaluar integracion con GitHub Workflow Agent para trazabilidad de issues o PRs.

---

## 25. Analisis de impacto entre artefactos

| Artefacto | Impacto | Accion requerida |
| --- | --- | --- |
| `docs/capabilities/consolidation-agent/project_brief.md` | Brief de capacidad actualizado tras Architecture Gate | Mantener como fuente de alcance y modo. |
| `docs/capabilities/consolidation-agent/context_refs.md` | Nuevo indice de fuentes | Mantener actualizado si cambia el contexto. |
| `docs/capabilities/consolidation-agent/sdd_readiness_assessment.md` | Readiness actualizado con QA Gate T-007, Architecture creada, review T-010 y QA Gate T-011 | Mantener como fuente de estado vigente. |
| `docs/capabilities/consolidation-agent/tasks.md` | Backlog actualizado con T-008 a T-011 | Mantener como fuente de decisiones y condiciones. |
| `docs/capabilities/index.md` | Requiere fila de routing para nueva capacidad | Actualizacion de catalogo, no normativa. |
| `specs/capabilities/index.md` | Requiere fila de routing para nueva spec | Actualizacion de catalogo, no normativa. |
| `AGENTS.md` | No debe actualizarse todavia | Crear agente real requiere capacidad futura. |
| `.github/agents/` | No debe actualizarse todavia | Definicion canonica futura pendiente. |
| `.codex/agents/` | No debe actualizarse todavia | Adaptador futuro pendiente. |
| `specs/capabilities/consolidation-agent/arch-001-consolidation-agent.md` | Architecture documental creada, revisada y validada por QA Gate | Mantener como arquitectura conceptual vigente. |
| Baselines cerrados | Usados como contexto | No modificar. |

---

## 26. Related Artifacts

| Artifact | Relationship |
| --- | --- |
| Project Brief | `docs/capabilities/consolidation-agent/project_brief.md` |
| Context References | `docs/capabilities/consolidation-agent/context_refs.md` |
| Readiness | `docs/capabilities/consolidation-agent/sdd_readiness_assessment.md` |
| Architecture | `specs/capabilities/consolidation-agent/arch-001-consolidation-agent.md` |
| Backlog | `docs/capabilities/consolidation-agent/tasks.md` |
| Workflow | No creado en esta fase. |
| Eval | No creado en esta fase. |
| Gate | No creado en esta fase. |

---

## Definition of Done

La specification esta completa cuando:

- el objetivo esta definido;
- el alcance esta definido;
- los limites estan definidos;
- los inputs y outputs estan definidos;
- el flujo operativo esta definido;
- las decisiones permitidas y prohibidas estan definidas;
- la integracion con otros agentes esta definida;
- los riesgos, dependencias, errores recuperables y reentradas estan documentados;
- existen criterios de aceptacion verificables;
- no existe implementacion ni reorganizacion fisica.