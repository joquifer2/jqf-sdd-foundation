# Plan de tareas - Consolidation Agent

## Metadatos

| Campo | Valor |
| --- | --- |
| Plan ID | TASKPLAN-001 |
| Capacidad | Consolidation Agent |
| Brief de proyecto relacionado | `docs/capabilities/consolidation-agent/project_brief.md` |
| Referencias de contexto relacionado | `docs/capabilities/consolidation-agent/context_refs.md` |
| Specification relacionada | `specs/capabilities/consolidation-agent/spec-001-consolidation-agent.md` |
| Architecture relacionada | `specs/capabilities/consolidation-agent/arch-001-consolidation-agent.md` |
| Estado | Closed with conditions |
| Fase SDD actual | Closed with conditions after Development MVP |
| Responsable | Jordi Quiroga |
| Creado por | Specification Agent |
| Ultima actualizacion | 2026-08-02 |

---

## 1. Objetivo

Registrar el backlog inicial necesario para revisar, validar y preparar la evolucion controlada de la capacidad `Consolidation Agent`.

Este plan registra que Architecture documental fue autorizada, creada, revisada y validada por QA Gate T-011. No autoriza Development, scripts, workflows, tools, agente real, adaptador Codex, consolidaciones reales ni reorganizacion fisica del repositorio.

---

## 2. Artefactos fuente

| Artefacto | Rol en el plan |
| --- | --- |
| `docs/capabilities/consolidation-agent/project_brief.md` | Define problema, alcance, modo y restricciones. |
| `docs/capabilities/consolidation-agent/context_refs.md` | Indexa fuentes y baseline cerrado relacionado. |
| `specs/capabilities/consolidation-agent/spec-001-consolidation-agent.md` | Define comportamiento esperado del futuro agente. |
| `docs/capabilities/consolidation-agent/sdd_readiness_assessment.md` | Evalua readiness y registra gates T-007 y T-011. |
| `specs/capabilities/consolidation-agent/arch-001-consolidation-agent.md` | Define arquitectura documental conceptual de la capacidad. |
| `specs/capabilities/project-consolidation-and-closure/spec-001-sdd-project-consolidation-and-closure.md` | Baseline de proceso de consolidacion. |
| `specs/capabilities/project-consolidation-and-closure/arch-001-sdd-project-consolidation-and-closure.md` | Arquitectura documental de cierre. |
| `docs/capabilities/project-consolidation-and-closure/closure_handover.md` | Handover de baseline cerrado relacionado. |

---

## 3. Reglas de planificacion

- Toda tarea debe permanecer en la fase SDD autorizada.
- Ninguna tarea autoriza Development.
- Las tareas no deben modificar documentos cerrados de capacidades previas.
- Las tareas no deben crear implementacion ni automatizacion.
- Las tareas no deben crear definicion canonica del agente ni adaptador Codex.
- Las tareas no deben mover, eliminar, renombrar ni reorganizar archivos.
- Cualquier decision fisica, ejecutable u operativa debe quedar como pendiente de fase futura autorizada.

---

## 4. Bloques de trabajo

1. Creacion de artefactos iniciales.
2. Revision de specification.
3. Validacion inicial de readiness.
4. Decision humana sobre Architecture.
5. Architecture documental autorizada, creada, revisada y validada.
6. Decision humana posterior si procede.

---

## 5. Tareas

| ID | Tarea | Tipo | Agente responsable | Dependencias | Criterios de aceptacion | Estado |
| --- | --- | --- | --- | --- | --- | --- |
| T-001 | Crear Brief de proyecto de la capacidad en estructura aislada. | Specification | Specification Agent | Request inicial | Brief existe, declara SDD Full y no modifica baselines cerrados. | Completed |
| T-002 | Crear Referencias de contexto de la capacidad. | Specification / Documentation | Specification Agent | T-001 | Context refs indexa fuentes, baseline cerrado y restricciones sin duplicar expedientes. | Completed |
| T-003 | Crear `SPEC-001 - Consolidation Agent`. | Specification | Specification Agent | T-001; T-002 | La spec cubre proposito, responsabilidades, limites, inputs, outputs, flujo, decisiones, integraciones, errores y reentradas. | Completed |
| T-004 | Crear readiness assessment inicial. | Specification / Validation prep | Specification Agent | T-003 | Readiness inicial existe y declara que Architecture/Development no estan autorizados. | Completed |
| T-005 | Crear backlog inicial de tareas. | Planning | Specification Agent | T-001 a T-004 | Backlog inicial existe con tareas trazables y sin autorizacion de Development. | Completed |
| T-006 | Revisar coherencia de artefactos iniciales contra baseline cerrado y restricciones. | Review | Reviewer Agent | T-001 a T-005 | Decision `Approved with minor changes`; correcciones menores de wording aplicadas; no se autoriza Development. | Completed |
| T-007 | Validar readiness inicial para posible decision de Architecture. | Validation | QA Gate Agent | T-006 | Decision `Pass with minor conditions`; Architecture requiere aprobacion humana explicita; Development permanece no autorizado. | Completed |
| T-008 | Decidir si se autoriza Architecture documental de la capacidad. | Governance | Jordi Quiroga | T-007 | Decision humana explicita `Autorizo, adelante [@Architect Agent]`; Development permanece no autorizado. | Completed |
| T-009 | Crear `ARCH-001 - Consolidation Agent`. | Architecture | Architect Agent | T-008 | Architecture conceptual existe sin implementacion ni agente real. | Completed |
| T-010 | Revisar Architecture si existe. | Review | Reviewer Agent | T-009 | Decision `Approved with minor corrections` registrada; correcciones aplicadas. | Completed |
| T-011 | Validar readiness de Architecture si existe. | Validation | QA Gate Agent | T-010 | Decision `Pass with minor conditions` registrada; siguiente paso requiere decision humana explicita. | Completed |

---

## 6. Decisiones abiertas representadas

| Decision | Impacto | Representada por |
| --- | --- | --- |
| Forma canonica futura del agente | Bloquea creacion en `.github/agents/` | SPEC-001 open questions |
| Adaptador Codex futuro | Bloquea seleccion operativa del agente en Codex | SPEC-001 future considerations |
| Template de reporte del agente | Afecta repetibilidad de consolidacion | SPEC-001 open questions |
| Gate para crear agente real | Bloquea Development futuro | Readiness / future QA |
| Reorganizacion fisica propuesta | Requiere capacidad especifica autorizada | SPEC-001 constraints |

---

## 7. Orden recomendado

```text
T-001
  ↓
T-002
  ↓
T-003
  ↓
T-004
  ↓
T-005
  ↓
T-006
  ↓
T-007
  ↓
T-008
```

T-009 a T-011 solo aplican si T-008 autoriza Architecture.

---

## 8. Dependencias criticas

| Dependencia | Impacto | Tareas afectadas |
| --- | --- | --- |
| No crear agente real | Bloquea `.github/agents/`, `.codex/agents/` y runtime | Todas |
| No modificar baselines cerrados | Bloquea propagacion sobre capacidades previas | Todas |
| Development no autorizado | Bloquea scripts, tools, workflows y automatizacion | Todas |
| Reorganizacion fisica no autorizada | Bloquea movimiento o renombrado de archivos | Todas |
| Review de Specification completada | QA Gate T-007 ejecutado | T-007 |
| QA Gate T-007 completado | Habilita decision humana informada sobre Architecture | T-008 |
| QA Gate T-011 completado | Habilita decision humana sobre siguiente fase documental | Futuro |

---

## 9. Riesgos de planificacion

| Riesgo | Impacto | Mitigacion |
| --- | --- | --- |
| Interpretar T-003 como creacion del agente | Alto | Mantener la spec como definicion de comportamiento. |
| Saltar review antes de Architecture | Alto | T-006 y T-007 son precondiciones. |
| Crear adaptador Codex prematuramente | Alto | Requiere fase futura autorizada. |
| Ejecutar reorganizacion fisica | Alto | Solo proposal-only en spec. |
| Duplicar funciones de QA Gate | Medio | El agente recomienda; QA decide gates. |

---

## 10. Siguiente paso recomendado

```text
Decision humana sobre la siguiente fase documental de `Consolidation Agent`.
```

Development permanece `NOT AUTHORIZED`.

---

## Definition of Done

El backlog esta actualizado cuando:

- registra los artefactos fuente;
- contiene tareas trazables;
- separa tareas completadas de pendientes;
- identifica siguiente agente recomendado;
- mantiene Development no autorizado.


---

## 11. QA Gate Decision - T-007

Decision: `Pass with minor conditions`.

Fecha: 2026-08-01.

Evaluador: QA Gate Agent.

Resultado:

- artefactos iniciales de Specification completos;
- Reviewer Agent aprobo con cambios menores y las correcciones fueron aplicadas;
- no hay implementacion prematura;
- no se crea agente real, adaptador Codex, scripts, tools, workflows ni reorganizacion fisica;
- Architecture queda pendiente de decision humana explicita;
- Development permanece `NOT AUTHORIZED`.

Condiciones:

1. Architecture requiere decision humana explicita.
2. No crear el `Consolidation Agent` real ni adaptadores en esta fase.
3. No crear scripts, tools, workflows, automatizaciones, consolidaciones reales ni reorganizacion fisica.
4. Development permanece `NOT AUTHORIZED`.

---

## 12. Architecture Authorization - T-008

Decision: `AUTHORIZED` solo para Architecture documental.

Fecha: 2026-08-01.

Fuente: solicitud humana `Autorizo, adelante [@Architect Agent]` posterior a QA Gate T-007.

Alcance autorizado:

- crear `ARCH-001 - Consolidation Agent`;
- definir componentes, interfaces, alternativas, decisiones y restricciones conceptuales;
- actualizar el expediente local y los indices de routing.

Fuera de autorizacion:

- Development;
- implementacion;
- creacion del agente real;
- definicion canonica en `.github/agents/`;
- adaptador Codex en `.codex/agents/`;
- scripts, tools, workflows o automatizaciones;
- consolidaciones reales;
- reorganizacion fisica;
- modificacion de baselines cerrados.

---

## 13. Architecture Execution - T-009

Estado: `Completed`.

Fecha: 2026-08-01.

Artefacto creado:

- `specs/capabilities/consolidation-agent/arch-001-consolidation-agent.md`.

Resultado:

- arquitectura documental creada;
- componentes e interfaces definidos conceptualmente;
- no se crea runtime, agente real, adaptador Codex, scripts, tools, workflows ni reorganizacion fisica;
- Development permanece `NOT AUTHORIZED`.

---

## 14. Reviewer Decision - T-010

Decision: `Approved with minor corrections`.

Fecha: 2026-08-01.

Evaluador: Reviewer Agent.

Artefactos revisados:

- `specs/capabilities/consolidation-agent/arch-001-consolidation-agent.md`
- `specs/capabilities/consolidation-agent/spec-001-consolidation-agent.md`
- `docs/capabilities/consolidation-agent/tasks.md`
- `docs/capabilities/consolidation-agent/sdd_readiness_assessment.md`
- `docs/capabilities/consolidation-agent/context_refs.md`
- `docs/capabilities/index.md`

Hallazgos:

- No se detectan contradicciones criticas entre `SPEC-001` y `ARCH-001`.
- La Architecture mantiene el alcance conceptual/documental.
- No introduce runtime, scripts, workflows, agente real, adaptador Codex, consolidaciones reales ni reorganizacion fisica.
- Se detectaron referencias menores a nombres de componentes no presentes en la tabla principal de arquitectura.

Correcciones aplicadas:

- Alineadas las referencias `Recommendation Engine` y `Output Package Builder` con los componentes documentados en `ARCH-001`.
- Actualizado el expediente para reflejar que T-010 queda completada.
- Actualizado el siguiente paso valido hacia QA Gate Agent en ese momento; T-011 queda completada posteriormente.

Resultado:

- T-010 queda `Completed`.
- Development permanece `NOT AUTHORIZED`.
- T-011 queda completada posteriormente; siguiente paso valido: decision humana sobre la siguiente fase documental.
---

## 15. QA Gate Decision - T-011

Decision: `Pass with minor conditions`.

Fecha: 2026-08-01.

Evaluador: QA Gate Agent.

Gate evaluado:

Architecture readiness for `Consolidation Agent`.

Fase actual:

`Architecture`.

Fase destino:

Decision humana sobre siguiente fase documental. Development no queda autorizado.

Artefactos revisados:

- `docs/capabilities/consolidation-agent/project_brief.md`
- `docs/capabilities/consolidation-agent/context_refs.md`
- `specs/capabilities/consolidation-agent/spec-001-consolidation-agent.md`
- `specs/capabilities/consolidation-agent/arch-001-consolidation-agent.md`
- `docs/capabilities/consolidation-agent/sdd_readiness_assessment.md`
- `docs/capabilities/consolidation-agent/tasks.md`
- `docs/capabilities/index.md`
- `specs/capabilities/index.md`
- `.github/instructions/sdd.instructions.md`
- `.github/agents/qa-gate.agent.md`

Evidencias encontradas:

- `SDD Mode` declarado como `SDD Full`.
- `ARCH-001` existe, esta trazado a `SPEC-001` y fue revisado en T-010.
- T-008 registra autorizacion humana explicita para Architecture documental.
- T-009 registra creacion de Architecture sin runtime ni agente real.
- No hay cambios en `.github/agents/` ni `.codex/agents/` para crear `Consolidation Agent`.
- No hay scripts, tools, workflows, automatizaciones, consolidaciones reales ni reorganizacion fisica en alcance.

Criterios cumplidos:

- Fase actual identificada.
- Artefactos obligatorios de Architecture existen.
- Architecture y Specification son coherentes.
- Reviewer Agent emitio decision favorable con correcciones menores aplicadas.
- Las dependencias y restricciones criticas estan documentadas.
- El siguiente paso queda identificado.

Criterios no cumplidos:

- No existe autorizacion humana para crear el agente real, definicion canonica, adaptador Codex, scripts, workflows, tools ni Development.
- No existe todavia decision humana para iniciar una fase posterior concreta.

Bloqueos:

- Development permanece `NOT AUTHORIZED`.
- Creacion del `Consolidation Agent` real permanece no autorizada.
- Reorganizacion fisica permanece no autorizada.

Condiciones:

1. Cualquier fase posterior requiere decision humana explicita.
2. Crear definicion canonica en `.github/agents/` requiere capacidad o fase futura autorizada.
3. Crear adaptador Codex en `.codex/agents/` requiere definicion canonica previa y autorizacion explicita.
4. Scripts, tools, workflows, automatizaciones o runtime solo pueden evaluarse en Development autorizado.
5. Los baselines cerrados permanecen inalterados.

Recomendacion:

Solicitar decision humana sobre la siguiente fase documental: planificacion posterior, documentation governance, o una nueva capacidad especifica para crear el agente real.

Autorizacion de Development:

`NOT AUTHORIZED`.

---

# 16. Development Planning Addendum - Consolidation Agent

## Proposito

Este anexo actualiza el expediente local de `Consolidation Agent` con un plan trazable para una implementacion futura derivada de `SPEC-001` y `ARCH-001`.

Esta intervencion es exclusivamente de Planning. No crea el agente real, no crea definicion canonica en `.github/agents/`, no crea adaptador Codex en `.codex/agents/`, no crea scripts, tools, workflows ni automatizaciones, no ejecuta consolidaciones reales, no modifica baselines cerrados y no inicia `Repository Physical Normalization`.

Development permanece `NOT AUTHORIZED` hasta autorizacion humana explicita posterior y evaluacion favorable de Development readiness.

## Artefactos fuente usados

| Artefacto | Uso |
| --- | --- |
| `docs/capabilities/consolidation-agent/project_brief.md` | Fuente de alcance, restricciones y `SDD Full`. |
| `docs/capabilities/consolidation-agent/context_refs.md` | Indice local de fuentes, jerarquia y decisiones pendientes. |
| `docs/capabilities/consolidation-agent/sdd_readiness_assessment.md` | Estado vigente tras QA Gate T-011. |
| `specs/capabilities/consolidation-agent/spec-001-consolidation-agent.md` | Fuente principal de comportamiento, limites, inputs, outputs, errores y reentradas. |
| `specs/capabilities/consolidation-agent/arch-001-consolidation-agent.md` | Fuente principal de componentes, interfaces, decisiones y restricciones. |
| `specs/capabilities/project-consolidation-and-closure/spec-001-sdd-project-consolidation-and-closure.md` | Baseline cerrado del proceso de Consolidation y Closed. |
| `specs/capabilities/project-consolidation-and-closure/arch-001-sdd-project-consolidation-and-closure.md` | Baseline cerrado de arquitectura documental de cierre. |
| `docs/capabilities/project-consolidation-and-closure/closure_handover.md` | Handover cerrado; registra deuda RD-001 sobre el futuro agente y RD-003 sobre normalizacion fisica. |
| `docs/capabilities/foundation-derivation-and-project-initialization/closure_handover.md` | Handover cerrado; confirma `Consolidation Agent` y `Repository Physical Normalization` como capacidades futuras separadas. |
| `.github/instructions/sdd.instructions.md` | Reglas vigentes de fases, `SDD Modes`, gates, Consolidation y precedencia documental. |
| `AGENTS.md` | Catalogo de agentes y regla de definiciones canonicas en `.github/agents/`. |
| `.github/agents/tasks-planner.agent.md` | Definicion canonica del agente usado para este plan. |

No existe template oficial especifico de `tasks.md`; se usa estructura inferida segun convenciones SDD y backlog existente.

## Alcance minimo de primera implementacion futura

Si una fase posterior autoriza Development, el primer incremento debe limitarse a:

1. Resolver decisiones humanas previas estrictamente necesarias.
2. Crear la definicion canonica documental del `Consolidation Agent`, si se autoriza.
3. Registrar el agente en catalogos documentales necesarios, solo si se autoriza.
4. Crear adaptador Codex solo si se aprueba como parte del alcance minimo o como tarea posterior.
5. Ejecutar validaciones estaticas documentales.
6. Ejecutar validacion retrospectiva no destructiva sobre SDD Modes.
7. Preparar handover y paquete para review/QA.

Fuera del alcance minimo:

- scripts, tools, workflows, automatizaciones o runtime;
- movimiento, renombrado o eliminacion de archivos;
- cambios en baselines cerrados;
- consolidaciones reales de capacidades;
- Repository Physical Normalization;
- autorizacion automatica de gates, cierre o Development.

## Bloques de trabajo futuros

| Bloque | Nombre | Proposito | Estado |
| --- | --- | --- | --- |
| B-01 | Decisiones humanas previas | Resolver alcance, ubicacion, adapter, reporte y limites antes de crear el agente real. | Planned - requiere autorizacion |
| B-02 | Definicion canonica del agente | Crear la definicion documental canonica, si Development queda autorizado. | Planned - Development no autorizado |
| B-03 | Adaptador Codex opcional | Crear adaptador solo despues de definicion canonica y autorizacion explicita. | Planned - condicional |
| B-04 | Inputs, outputs y reporte | Formalizar inputs obligatorios/opcionales, outputs permitidos y formato de reporte. | Planned - requiere decision |
| B-05 | Validaciones estaticas | Verificar coherencia documental, naming, precedencia y ausencia de implementacion prematura. | Planned |
| B-06 | Validacion retrospectiva sobre SDD Modes | Comprobar comportamiento esperado sobre baseline cerrado sin aplicar cambios. | Planned - no destructivo |
| B-07 | Handover | Preparar handover, deuda residual y puntos de reentrada de la implementacion autorizada. | Planned - condicional |
| B-08 | Review y QA final | Revisar el plan/paquete y evaluar readiness sin autorizar Development automaticamente. | Planned |

## Tareas futuras trazables

| ID | Bloque | Tarea | Tipo | Trazabilidad | Responsable | Dependencias | Criterios de aceptacion | Estado |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| T-012 | B-01 | Emitir decision humana sobre si se autoriza preparar Development Gate para crear el agente real. | Governance | QA T-011; SPEC §24; ARCH §15 | Jordi Quiroga | T-011 | Decision explicita registrada; autoriza Development solo para MVP y alcance aprobado. | Completed |
| T-013 | B-01 | Resolver ubicacion canonica exacta y naming de la definicion del agente. | Governance | AGENTS.md; SPEC §23; ARCH AD-006 | Jordi Quiroga / Documentation Agent | T-012 | Ubicacion definida como `.github/agents/consolidation.agent.md`; ID `SDD-AGENT-010`. | Completed |
| T-014 | B-01 | Resolver necesidad y alcance del adaptador Codex. | Governance | SPEC §24; ARCH §14 | Jordi Quiroga | T-012; T-013 | Adaptador Codex incluido en MVP como puente a la definicion canonica, sin segunda fuente de verdad. | Completed |
| T-015 | B-01 | Resolver formato del `Consolidation Agent Report`. | Governance / Documentation | ARCH §7; SPEC §7; SPEC §23 | Jordi Quiroga / Documentation Agent | T-012 | MVP usa reporte/secciones en handover, evidence index y readiness; template standalone queda deuda futura no bloqueante. | Completed with residual debt |
| T-016 | B-01 | Resolver comportamiento `proposal-only` frente a cambios documentales autorizados. | Governance | SPEC R-006; SPEC §11-12; ARCH §5.8 | Jordi Quiroga / QA Gate Agent | T-012 | Cambios de catalogo y adaptador quedan autorizados por MVP; reorganizacion fisica y cambios de baseline permanecen `proposal-only`. | Completed |
| T-017 | B-01 | Confirmar limites con `Repository Physical Normalization`. | Governance / Architecture | ARCH §5.9; handovers cerrados; SPEC BR-005 | Jordi Quiroga / Architect Agent | T-012 | Confirmado fuera de alcance; todo movimiento fisico requiere capacidad separada. | Completed |
| T-018 | B-01 | Definir Development Gate propuesto para el alcance minimo. | Planning / Validation prep | QA T-011; SDD instructions §3.3; SPEC FR-012 | Tasks Planner Agent / QA Gate Agent | T-012 a T-017 | Gate re-evaluado tras autorizacion humana; MVP puede implementarse con Review/QA finales obligatorios. | Completed |
| T-019 | B-02 | Crear definicion canonica documental del `Consolidation Agent`. | Development / Documentation | SPEC §8-17; ARCH §4-7; AGENTS.md | Documentation Agent o agente autorizado | T-018; autorizacion humana de Development | Archivo canonico creado en `.github/agents/consolidation.agent.md`; sin runtime ni automatizacion. | Completed |
| T-020 | B-02 | Trazar la definicion canonica contra `SPEC-001` y `ARCH-001`. | Documentation | SPEC AC-001 a AC-009; ARCH AD-001 a AD-006 | Documentation Agent | T-019 | Responsabilidades, limites, flujo, inputs/outputs, errores y DoD trazados a spec/architecture. | Completed |
| T-021 | B-02 | Actualizar catalogo o routing documental aplicable del SDD Harness, si se autoriza. | Documentation | AGENTS.md; ARCH impact §13 | Documentation Agent | T-019; decision humana especifica | Catalogos/routing actualizados: `AGENTS.md`, `.github/agents/README.md`, `.codex/agents/README.md`, indices de capacidades. | Completed |
| T-022 | B-03 | Crear adaptador Codex del `Consolidation Agent`, si se autoriza. | Development / Documentation | SPEC §24; ARCH AD-006; AGENTS.md | Documentation Agent o agente autorizado | T-014; T-019; autorizacion humana de Development | Adaptador `.codex/agents/consolidation.toml` creado y declara que la definicion canonica prevalece. | Completed |
| T-023 | B-03 | Validar coherencia entre adaptador Codex y definicion canonica. | Validation | AGENTS.md; SPEC limits; ARCH §6.4 | Reviewer Agent / Documentation Agent | T-022 | Adaptador mantiene limites de la definicion canonica y no introduce capacidades adicionales. | Completed |
| T-024 | B-04 | Definir inputs obligatorios y opcionales del agente en la definicion final. | Documentation | SPEC §6; ARCH §5.2 | Documentation Agent | T-019 | Inputs obligatorios, condicionales y discovery-only definidos; ausencia de input obligatorio produce `Blocked`. | Completed |
| T-025 | B-04 | Definir outputs permitidos y salidas prohibidas del agente. | Documentation | SPEC §7; SPEC §11-12; ARCH §7 | Documentation Agent | T-019 | Outputs definidos como propuesta, borrador, reporte o handoff no ejecutable. | Completed |
| T-026 | B-04 | Definir tratamiento de errores, deuda residual y puntos de reentrada. | Documentation | SPEC §14-15; ARCH §5.6; baseline de cierre | Documentation Agent | T-019 | Errores recuperables, deuda residual y reentradas definidos en la definicion canonica. | Completed |
| T-027 | B-05 | Ejecutar revision estatica de ausencia de implementacion prematura. | Validation | Project Brief; SPEC §18; ARCH §9 | Reviewer Agent / QA Gate Agent | T-019 a T-026 | Validacion estatica confirma ausencia de scripts, workflows, tools, runtime, consolidaciones reales y movimientos fisicos. | Completed |
| T-028 | B-05 | Ejecutar revision estatica de precedencia documental y limites entre agentes. | Review | SDD instructions §11.5; SPEC §13; ARCH §6.4 | Reviewer Agent | T-019 a T-026 | Validacion estatica confirma que el agente no sustituye otros agentes ni decision humana. | Completed |
| T-029 | B-06 | Preparar validacion retrospectiva no destructiva sobre SDD Modes. | Planning / Validation prep | SPEC FR-011; baseline de cierre §13; SDD Modes baseline | Tasks Planner Agent / QA Gate Agent | T-019; T-024 a T-026 | Caso retrospectivo SDD Modes preparado sin modificar baseline cerrado. | Completed |
| T-030 | B-06 | Ejecutar validacion retrospectiva documental sobre SDD Modes sin aplicar cambios. | Validation | SPEC FR-001 a FR-012; ARCH pipeline | QA Gate Agent / Reviewer Agent | T-029; autorizacion de validacion | Validacion retrospectiva ejecutada; resultado `Eligible with conditions`; no se modifico baseline. | Completed |
| T-031 | B-06 | Registrar hallazgos de validacion retrospectiva como evidencia o deuda futura. | Documentation | SPEC R-003; ARCH §5.6 | Documentation Agent | T-030 | Hallazgos registrados en `evidence_index.md` y deuda futura en `residual_debt.md`. | Completed |
| T-032 | B-07 | Preparar handover de la implementacion autorizada del agente. | Documentation | ARCH §5.7; closure handover template | Documentation Agent | T-027 a T-031 | `closure_handover.md` preparado como cierre candidato pendiente de Reviewer y QA final. | Completed |
| T-033 | B-07 | Preparar propuesta de Closure/Consolidation posterior si aplica. | Planning / Validation prep | Baseline de cierre; gates | Tasks Planner Agent / QA Gate Agent | T-032 | Propuesta de cierre formal preparada; cierre definitivo depende de Reviewer y QA Gate final. | Completed |
| T-034 | B-08 | Reviewer Agent revisa el plan y paquete Development. | Review | Este `tasks.md`; SPEC-001; ARCH-001; agente canonico; adaptador; handover/evidencia/deuda | Reviewer Agent | T-019 a T-033 | Decision `Approved`; no hay cambios fuera de alcance ni implementacion prematura. | Completed |
| T-035 | B-08 | QA Gate Agent evaluo Development completion y Closure readiness con decision `Pass with conditions`. | Validation | Review T-034; QA T-011; Development Gate propuesto; validacion retrospectiva | QA Gate Agent | T-034 | Decision `Pass with conditions`; capacidad cerrada con deuda residual visible y reentradas. | Completed |

## Decisiones humanas requeridas

| Decision | Estado | Motivo | Bloquea |
| --- | --- | --- | --- |
| Autorizar preparacion de Development Gate | Resuelta | Decision humana del 2026-08-02 autorizo Development del MVP. | T-018 completada |
| Ubicacion y naming exacto de la definicion canonica | Resuelta | `.github/agents/consolidation.agent.md`; ID `SDD-AGENT-010`. | T-019 completada |
| Crear o no adaptador Codex en el primer alcance | Resuelta | Adaptador incluido como `.codex/agents/consolidation.toml`. | T-022 completada |
| Formato del `Consolidation Agent Report` | Resuelta para MVP / deuda futura | MVP usa handover/evidence/readiness; template standalone queda CA-RD-001. | T-024 a T-026 completadas |
| Alcance de outputs aplicables frente a `proposal-only` | Resuelta | Catalogos autorizados; reorganizacion fisica y cambios de baseline siguen `proposal-only`. | T-021 y T-025 completadas |
| Evidencia minima para reorganizacion fisica propuesta | Resuelta como fuera de alcance | Requiere capacidad separada; deuda CA-RD-003. | T-017 y T-030 completadas |
| Validacion retrospectiva permitida sobre SDD Modes | Resuelta | Ejecutada como no destructiva con resultado `Eligible with conditions`; deuda CA-RD-004. | T-029 a T-031 completadas |

## Dependencias criticas

| Dependencia | Impacto | Tareas afectadas |
| --- | --- | --- |
| Autorizacion humana posterior | Bloquea Development, agente real, definicion canonica y adaptador Codex. | T-012 a T-035 |
| Development Gate favorable | Bloquea creacion de archivos de agente real y adaptador. | T-019 a T-023 |
| Definicion canonica previa | Bloquea adaptador Codex. | T-022; T-023 |
| Decision sobre formato de reporte | Bloquea repetibilidad del output del agente. | T-015; T-024 a T-026 |
| Decision sobre comportamiento `proposal-only` | Bloquea aplicacion de cambios documentales por agentes responsables. | T-016; T-021; T-025 |
| No modificar baselines cerrados | Impide tocar SDD Modes, Project Consolidation and Closure y Foundation Derivation salvo nueva autorizacion. | Todas |
| Repository Physical Normalization separada | Impide mover, renombrar, eliminar o normalizar fisicamente artefactos. | T-017; T-027; T-030 |
| Review antes de QA final | QA de readiness depende de revision del plan o paquete. | T-034; T-035 |

## Riesgos

| Riesgo | Impacto | Mitigacion |
| --- | --- | --- |
| Interpretar este plan como autorizacion de Development | Alto | Estado explicito `Development NOT AUTHORIZED`; T-012/T-018/T-035 requieren decision y gate. |
| Crear adaptador Codex antes de definicion canonica | Alto | T-022 depende de T-019 y decision T-014. |
| El agente asume funciones de QA Gate o Reviewer | Alto | T-028 valida limites; SPEC y ARCH enrutan decisiones hacia agentes responsables. |
| El reporte se convierte en cambio aplicado automaticamente | Alto | T-016 y T-025 separan outputs `proposal-only` de cambios autorizados. |
| Validacion retrospectiva modifica SDD Modes | Alto | T-029/T-030 se definen como no destructivas y sin cambios de baseline. |
| Repository Physical Normalization se mezcla con el agente | Alto | T-017 confirma capacidad separada; solo propuesta `proposal-only`. |
| Deuda residual se oculta bajo handover resumido | Medio | T-026 y T-032 exigen deuda visible y puntos de reentrada. |
| Se introducen scripts o workflows por conveniencia | Alto | Fuera del alcance minimo; T-027 verifica ausencia de implementacion prematura. |

## Development Gate propuesto

El Development Gate posterior debe evaluar, como minimo:

- decision humana explicita que solicite evaluar Development;
- `SPEC-001` y `ARCH-001` revisados y vigentes;
- decisiones T-013 a T-017 resueltas o registradas como bloqueos aceptados;
- alcance minimo definido y sin scripts/tools/workflows/runtime;
- archivos permitidos claramente listados;
- plan de validacion estatica definido;
- validacion retrospectiva no destructiva acotada;
- limites con `Repository Physical Normalization` confirmados;
- criterio de rollback documental o correccion definido;
- Reviewer Agent disponible para revisar el plan o paquete.

Resultados posibles:

- `Pass`: puede recomendar iniciar Development, pero requiere autorizacion humana explicita posterior.
- `Pass with conditions`: puede recomendar iniciar solo tareas condicionadas.
- `Fail`: no se debe iniciar Development.
- `Blocked`: faltan decisiones, artefactos o evidencias.

## Definition of Done del plan

Este plan queda listo cuando:

- conserva el historial T-001 a T-011;
- deriva tareas futuras trazables a `SPEC-001`, `ARCH-001`, gates y handovers cerrados;
- separa decisiones previas, definicion canonica, adaptador Codex, validaciones, validacion retrospectiva, handover y QA final;
- identifica dependencias, responsable y criterios de aceptacion por tarea;
- marca decisiones humanas requeridas sin inventarlas;
- define alcance minimo de primera implementacion;
- registra riesgos y gates;
- mantiene Development como `NOT AUTHORIZED`;
- no modifica artefactos fuera del expediente local de `Consolidation Agent`.

## Siguiente paso recomendado

```text
Superado por Development MVP, Reviewer T-034 y QA Gate T-035. Ver secciones 17 a 22.
```

---

## 17. Human Development Authorization - T-012

Decision: `AUTHORIZED` para iniciar Development del MVP de `Consolidation Agent`.

Fecha: 2026-08-02.

Fuente: decision humana explicita posterior a QA Gate T-035 inicial, que habia quedado `Blocked` por ausencia de autorizacion humana.

Alcance autorizado:

- implementacion del MVP definido en `SPEC-001`, `ARCH-001` y Task Plan aprobado;
- exclusivamente dentro del alcance aprobado;
- trazabilidad obligatoria con `SPEC-001` y `ARCH-001`.

Fuera de autorizacion:

- cambios normativos;
- reorganizacion fisica del repositorio;
- `Repository Physical Normalization`;
- modificaciones de baselines cerrados;
- funcionalidades no contempladas en la Specification aprobada.

Obligatorio al finalizar Development:

- Reviewer Agent;
- QA Gate Agent;
- validacion retrospectiva usando SDD Modes como caso de prueba;
- cierre formal de la capacidad.

---

## 18. Development Execution - T-019 to T-033

Estado: `MVP implemented and closed with conditions`.

Fecha: 2026-08-02.

Archivos creados:

- `.github/agents/consolidation.agent.md`
- `.codex/agents/consolidation.toml`
- `docs/capabilities/consolidation-agent/evidence_index.md`
- `docs/capabilities/consolidation-agent/residual_debt.md`
- `docs/capabilities/consolidation-agent/closure_handover.md`

Archivos actualizados:

- `AGENTS.md`
- `.github/agents/README.md`
- `.codex/agents/README.md`
- `docs/capabilities/index.md`
- `specs/capabilities/index.md`
- `docs/capabilities/consolidation-agent/tasks.md`
- `docs/capabilities/consolidation-agent/sdd_readiness_assessment.md`

Resultado:

- definicion canonica creada como agente metodologico del SDD Harness;
- adaptador Codex creado como puente, no como segunda fuente de verdad;
- catalogos de routing actualizados;
- no se crean scripts, tools, workflows, runtime ni automatizaciones;
- no se ejecutan consolidaciones reales;
- no se modifica ningun baseline cerrado;
- no se mueve, renombra ni elimina ningun archivo;
- `Repository Physical Normalization` permanece fuera de alcance.

---

## 19. Retrospective Validation - SDD Modes

Resultado: `Eligible with conditions`.

Fecha: 2026-08-02.

Caso usado:

- `SDD Modes` como baseline cerrado y caso retrospectivo no destructivo.

Artefactos observados sin modificar:

- `docs/project_brief.md`
- `docs/context_refs.md`
- `docs/tasks.md`
- `docs/sdd_readiness_assessment.md`
- `specs/spec-001-sdd-modes.md`
- `specs/spec-001-sdd-modes.architecture.md`

Hallazgos:

- El caso contiene Project Brief, Context References, Specification, Architecture, Tasks y Readiness.
- El modo `SDD Full` esta declarado y justificado.
- Existe evidencia de cierre metodologico y de deuda residual `VAL-001`.
- El agente podria clasificar baseline, expediente historico, evidencia y deuda sin modificar el baseline.
- La ausencia de un handover propio de SDD Modes implica condicion: la consolidacion retrospectiva no debe producir cierre nuevo ni reclasificar fisicamente el expediente sin una capacidad separada.

Decision de validacion retrospectiva:

`Eligible with conditions` para preparacion de reporte/propuesta. No se ejecuta consolidacion real ni cambio sobre SDD Modes.

---

## 20. Final Review and QA

Review y QA finales completados. Ver secciones 21 y 22.

---

## 21. Final Reviewer Decision - T-034

Decision: `Approved`.

Fecha: 2026-08-02.

Evaluador: Reviewer Agent.

Resultado:

- El MVP mantiene trazabilidad con `SPEC-001` y `ARCH-001`.
- La definicion canonica respeta responsabilidades, limites, inputs, outputs, errores y reentradas definidos.
- El adaptador Codex no crea segunda fuente de verdad.
- Los catalogos reflejan el nuevo agente sin introducir runtime ni automatizacion.
- No se detectan cambios en baselines cerrados.
- No se ejecuta reorganizacion fisica ni `Repository Physical Normalization`.
- La validacion retrospectiva sobre SDD Modes queda registrada como no destructiva.

Hallazgos criticos: ninguno.

Hallazgos importantes: ninguno.

Hallazgos menores: ninguno bloqueante.

---

## 22. Final QA Gate Decision - T-035

Decision: `Pass with conditions`.

Fecha: 2026-08-02.

Evaluador: QA Gate Agent.

Gate evaluado: Development completion and Closure readiness for `Consolidation Agent`.

Fase actual: `Development MVP implemented`.

Fase destino: `Closed with conditions`.

Criterios cumplidos:

- Existe autorizacion humana explicita de Development para MVP.
- `SPEC-001` y `ARCH-001` gobiernan el alcance.
- El agente canonico y el adaptador Codex existen.
- El paquete fue revisado por Reviewer Agent con decision `Approved`.
- La validacion retrospectiva sobre SDD Modes fue ejecutada y registrada como `Eligible with conditions`.
- No existen scripts, tools, workflows, runtime ni automatizaciones.
- No se modificaron baselines cerrados.
- No se ejecuto reorganizacion fisica.
- Deuda residual y puntos de reentrada quedan visibles.
- Handover de cierre existe.

Condiciones de cierre:

1. Development adicional requiere nueva decision humana y gate aplicable.
2. Template standalone de `Consolidation Agent Report` queda como deuda futura no bloqueante.
3. Automatizaciones de checks quedan fuera del MVP y requieren nueva capacidad.
4. `Repository Physical Normalization` permanece capacidad futura separada.
5. SDD Modes no fue modificado; cualquier consolidacion real sobre SDD Modes requiere reentrada separada.

Autorizacion posterior:

`Development additional NOT AUTHORIZED`.

Estado final:

`Closed with conditions`.