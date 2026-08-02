# Plan de tareas - Repository Physical Normalization

## Metadatos

| Campo | Valor |
| --- | --- |
| Plan ID | TASKPLAN-001 |
| Capacidad | Repository Physical Normalization |
| Brief de proyecto relacionado | `docs/capabilities/repository-physical-normalization/project_brief.md` |
| Referencias de contexto relacionado | `docs/capabilities/repository-physical-normalization/context_refs.md` |
| Specification relacionada | `specs/capabilities/repository-physical-normalization/spec-001-repository-physical-normalization.md` |
| Estado | Architecture |
| Fase SDD actual | Architecture |
| Responsable | Jordi Quiroga |
| Creado por | Specification Agent |
| Ultima actualizacion | 2026-08-02 |

---

## 1. Objetivo

Registrar el backlog inicial necesario para revisar, validar y preparar la evolucion controlada de la capacidad `Repository Physical Normalization`.

Este plan registra que Architecture documental fue autorizada por T-008. No autoriza Development, scripts, workflows, tools, automatizaciones, movimientos fisicos, renombres, copias, sustituciones, eliminaciones ni modificacion de baselines cerrados.

---

## 2. Artefactos fuente

| Artefacto | Rol en el plan |
| --- | --- |
| `docs/capabilities/repository-physical-normalization/project_brief.md` | Define problema, alcance, modo y restricciones. |
| `docs/capabilities/repository-physical-normalization/context_refs.md` | Indexa fuentes y baseline cerrado relacionado. |
| `specs/capabilities/repository-physical-normalization/spec-001-repository-physical-normalization.md` | Define proceso, reglas, estructura objetivo y limites. |
| `docs/capabilities/repository-physical-normalization/sdd_readiness_assessment.md` | Evalua readiness inicial de Specification. |
| `docs/capabilities/consolidation-agent/validations/sdd-modes-retrospective/consolidation_report.md` | Propuesta no ejecutable de aplicacion sobre `SDD Modes`. |
| `docs/capabilities/project-consolidation-and-closure/closure_handover.md` | Handover de baseline cerrado de consolidacion/cierre. |
| `docs/capabilities/consolidation-agent/closure_handover.md` | Handover que fija frontera con `Consolidation Agent`. |

---

## 3. Reglas de planificacion

- Toda tarea debe permanecer en la fase SDD autorizada.
- Architecture documental solo queda autorizada por T-008; ninguna tarea autoriza ampliarla mas alla de ARCH-001.
- Ninguna tarea autoriza Development.
- Las tareas no deben modificar documentos cerrados de capacidades previas.
- Las tareas no deben crear implementacion ni automatizacion.
- Las tareas no deben mover, copiar, renombrar, eliminar ni reorganizar archivos.
- Cualquier decision fisica, ejecutable u operativa debe quedar como pendiente de fase futura autorizada.

---

## 4. Bloques de trabajo

1. Creacion de artefactos iniciales.
2. Revision de Specification.
3. Validacion inicial de readiness.
4. Decision humana sobre Architecture.
5. Architecture documental futura, si se autoriza.
6. Planificacion/ejecucion futura, solo si gates y decisiones lo autorizan.

---

## 5. Tareas

| ID | Tarea | Tipo | Agente responsable | Dependencias | Criterios de aceptacion | Estado |
| --- | --- | --- | --- | --- | --- | --- |
| T-001 | Crear Brief de proyecto de la capacidad en estructura aislada. | Specification | Specification Agent | Request inicial | Brief existe, declara `SDD Full` y no modifica baselines cerrados. | Completed |
| T-002 | Crear Referencias de contexto de la capacidad. | Specification / Documentation | Specification Agent | T-001 | Context refs indexa fuentes, baseline cerrado, paquete retrospectivo y restricciones. | Completed |
| T-003 | Crear `SPEC-001 - Repository Physical Normalization`. | Specification | Specification Agent | T-001; T-002 | La spec cubre objetivos, reglas, estructura objetivo, compatibilidad, reversibilidad, SDD Modes y frontera con Consolidation Agent. | Completed |
| T-004 | Crear readiness assessment inicial. | Specification / Validation prep | Specification Agent | T-003 | Readiness inicial existe y declara que Architecture/Development/movimientos no estan autorizados. | Completed |
| T-005 | Crear backlog inicial de tareas. | Planning | Specification Agent | T-001 a T-004 | Backlog inicial existe con tareas trazables y sin autorizacion de Architecture/Development. | Completed |
| T-006 | Revisar coherencia de artefactos iniciales contra baseline cerrado y restricciones. | Review | Reviewer Agent | T-001 a T-005 | Decision `Approved with minor changes` registrada; no hay hallazgos criticos ni importantes; no se autoriza Development. | Completed |
| T-007 | Validar readiness inicial para posible decision de Architecture. | Validation | QA Gate Agent | T-006 | Decision `Pass with minor conditions` registrada; Architecture requiere aprobacion humana explicita; Development permanece no autorizado. | Completed |
| T-008 | Decidir si se autoriza Architecture documental de la capacidad. | Governance | Jordi Quiroga | T-007 | Decision humana explicita `Autorizacion de la Architecture documental` registrada. | Completed |
| T-009 | Crear `ARCH-001 - Repository Physical Normalization`, si se autoriza. | Architecture | Architect Agent | T-008 | Architecture conceptual existe sin ejecutar movimientos ni crear scripts. | Completed |
| T-010 | Definir reference map, movement plan y rollback plan como componentes documentales, si Architecture lo autoriza. | Architecture | Architect Agent | T-009 | Planes definidos en ARCH-001 como futuros no ejecutables. | Completed |
| T-011 | Revisar Architecture y plan documental, si existen. | Review | Reviewer Agent | T-009; T-010 | Decision `Approved with minor changes` registrada; compatibilidad, reversibilidad y ausencia de ejecucion confirmadas. | Completed |
| T-012 | Validar readiness de Architecture. | Validation | QA Gate Agent | T-011 | Decision `Pass with minor conditions` registrada; no autoriza Development ni ejecucion fisica. | Completed |

---

## 6. Decisiones abiertas representadas

| Decision | Impacto | Representada por |
| --- | --- | --- |
| Crear o no carpetas `baseline/` | Afecta estructura fisica objetivo | SPEC open questions |
| Estrategia de compatibilidad legacy | Bloquea movimientos seguros | SPEC CP/RV sections |
| Naming final de SDD Modes Architecture | Afecta coste de referencias | SPEC Section 16 |
| Formato de movement/reference/rollback plan | Bloquea Architecture ejecutiva | SPEC future considerations |
| Gate exacto para ejecucion fisica | Bloquea Development/Documentation ejecutiva | Readiness / tasks futuras |
| Agente ejecutor autorizado | Bloquea movimientos | Open questions |

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

T-009 a T-012 solo aplican si T-008 autoriza Architecture.

---

## 8. Dependencias criticas

| Dependencia | Impacto | Tareas afectadas |
| --- | --- | --- |
| No modificar baselines cerrados | Impide tocar SDD Modes y capacidades cerradas. | Todas |
| No ejecutar normalizacion fisica | Impide movimientos, renombres, copias, sustituciones y eliminaciones. | Todas |
| Architecture documental completada | Bloquea cualquier ejecucion hasta Review, QA y nueva autorizacion futura. | T-011 a T-012 |
| Reference map futuro | Bloquea ejecucion segura. | T-010 a T-012 |
| Reviewer antes de QA | QA depende de revision previa. | T-006; T-007; T-011; T-012 |
| Aprobacion humana explicita | Bloquea Architecture, Development y movimientos. | T-008+ |

---

## 9. Riesgos de planificacion

| Riesgo | Impacto | Mitigacion |
| --- | --- | --- |
| Interpretar SPEC como permiso de mover archivos | Alto | Reglas explicitas de no ejecucion en Brief, SPEC, Readiness y Tasks. |
| Mezclar Consolidation Agent con ejecucion fisica | Alto | Frontera documentada; agente propone, esta capacidad gobierna ejecucion futura. |
| Saltar reference map | Alto | T-010/T-012 dependen de mapa futuro. |
| Actualizar indices globales prematuramente | Medio | Tratado como impacto futuro, no como cambio automatico. |
| Crear scripts de conveniencia | Alto | Fuera de alcance hasta nueva capacidad Development. |

---

## 10. Siguiente paso recomendado

```text
Human decision on whether to authorize a future governed execution-preparation phase.
```

Development permanece `NOT AUTHORIZED`. No se autoriza normalizacion fisica.

---

## Definition of Done

El backlog inicial esta listo cuando:

- registra los artefactos fuente;
- contiene tareas trazables;
- separa tareas completadas, pendientes y no autorizadas;
- identifica siguiente agente recomendado;
- mantiene Development no autorizado y Architecture limitada a lo aprobado en T-008;
- no incluye ejecucion de normalizacion fisica.

---

## 11. Reviewer Decision - T-006

Decision: `Approved with minor changes`.

Fecha: 2026-08-02.

Evaluador: Reviewer Agent.

Artefactos revisados:

- `docs/capabilities/repository-physical-normalization/project_brief.md`
- `docs/capabilities/repository-physical-normalization/context_refs.md`
- `specs/capabilities/repository-physical-normalization/spec-001-repository-physical-normalization.md`
- `docs/capabilities/repository-physical-normalization/sdd_readiness_assessment.md`
- `docs/capabilities/repository-physical-normalization/tasks.md`

Resultado:

- No hay hallazgos criticos.
- No hay hallazgos importantes.
- Hallazgos menores documentales aplicados por Documentation Agent.
- Architecture documental fue autorizada por T-008 y completada en T-009/T-010.
- Development permanece `NOT AUTHORIZED`.
- No se ejecuta normalizacion fisica.

Cambios menores aplicados:

- `docs/capabilities/index.md` indexa `Repository Physical Normalization` como capacidad en `Specification`.
- `specs/capabilities/index.md` indexa `SPEC-001 - Repository Physical Normalization`.
- `sdd_readiness_assessment.md` refleja Reviewer T-006 y siguiente agente recomendado `QA Gate Agent`.

Siguiente paso valido:

```text
Human decision on whether to authorize a future governed execution-preparation phase.
```
---

## 12. QA Gate Decision - T-007

Decision: `Pass with minor conditions`.

Fecha: 2026-08-02.

Evaluador: QA Gate Agent.

Gate evaluado:

Specification readiness for `Repository Physical Normalization`.

Resultado:

- Los artefactos de Specification existen y son coherentes.
- Reviewer T-006 fue completado con cambios menores ya aplicados.
- Los indices globales registran la capacidad y la specification como catalogos no normativos.
- No existe implementacion prematura.
- No se modifican baselines cerrados.
- No se ejecuta normalizacion fisica.

Condiciones:

1. Architecture requiere decision humana explicita.
2. Development permanece `NOT AUTHORIZED`.
3. Cualquier movimiento, copia, renombre, sustitucion o eliminacion permanece `NOT AUTHORIZED`.
4. Una Architecture futura debe resolver compatibilidad legacy, reference map, movement plan y rollback plan antes de cualquier ejecucion.

Siguiente paso valido:

```text
Human decision on whether to authorize a future governed execution-preparation phase.
```
---

## 13. Architecture Authorization - T-008

Decision: `AUTHORIZED` solo para Architecture documental.

Fecha: 2026-08-02.

Fuente: solicitud humana `Autorizacion de la Architecture documental` posterior a QA Gate T-007.

Alcance autorizado:

- crear `ARCH-001 - Repository Physical Normalization`;
- definir estructura conceptual, componentes, interfaces, alternativas y decisiones;
- definir reference map, movement plan y rollback plan como componentes futuros no ejecutables;
- actualizar expediente local e indices no normativos.

Fuera de autorizacion:

- Development;
- normalizacion fisica;
- movimiento, copia, renombre, sustitucion o eliminacion de archivos;
- scripts, tools, workflows, runtime o automatizaciones;
- modificacion de baselines cerrados.

---

## 14. Architecture Execution - T-009/T-010

Estado: `Completed`.

Fecha: 2026-08-02.

Artefacto creado:

- `specs/capabilities/repository-physical-normalization/arch-001-repository-physical-normalization.md`.

Resultado:

- arquitectura documental creada;
- componentes e interfaces definidos;
- reference map, movement plan y rollback plan definidos como artefactos futuros no ejecutables;
- `SDD Modes` definido como piloto futuro sin ejecutar movimientos;
- no se crean scripts, tools, workflows, runtime ni automatizaciones;
- no se modifican baselines cerrados;
- no se mueve, copia, renombra, sustituye ni elimina ningun archivo.

Siguiente paso valido:

```text
Human decision on whether to authorize a future governed execution-preparation phase.
```
---

## 15. Architecture Reviewer Decision - T-011

Decision: `Approved with minor changes`.

Fecha: 2026-08-02.

Evaluador: Reviewer Agent.

Artefactos revisados:

- `specs/capabilities/repository-physical-normalization/arch-001-repository-physical-normalization.md`
- `docs/capabilities/repository-physical-normalization/project_brief.md`
- `docs/capabilities/repository-physical-normalization/context_refs.md`
- `specs/capabilities/repository-physical-normalization/spec-001-repository-physical-normalization.md`
- `docs/capabilities/repository-physical-normalization/sdd_readiness_assessment.md`
- `docs/capabilities/repository-physical-normalization/tasks.md`
- `docs/capabilities/index.md`
- `specs/capabilities/index.md`

Resultado:

- No hay hallazgos criticos.
- No hay hallazgos importantes.
- `ARCH-001` respeta `SDD Full`.
- `ARCH-001` esta trazada a `SPEC-001`.
- No introduce implementacion prematura.
- No autoriza Development.
- No ejecuta normalizacion fisica.
- No modifica baselines cerrados.

Cambios menores aplicados por Documentation Agent:

- `ARCH-001` marca como completada la actualizacion de indices globales no normativos.
- Readiness identifica el bloque QA T-007 como historico y superado por T-008.
- Este backlog marca T-011 como completada y T-012 como siguiente paso pendiente.

Siguiente paso valido:

```text
Human decision on whether to authorize a future governed execution-preparation phase.
```

Development permanece `NOT AUTHORIZED`. No se autoriza normalizacion fisica.
---

## 16. Architecture QA Gate Decision - T-012

Decision: `Pass with minor conditions`.

Fecha: 2026-08-02.

Evaluador: QA Gate Agent.

Gate evaluado:

Architecture readiness for `Repository Physical Normalization`.

Fase actual:

`Architecture`.

Fase destino:

Decision humana futura sobre siguiente fase documental o preparacion ejecutiva. Este gate no autoriza Development ni normalizacion fisica.

Artefactos revisados:

- `docs/capabilities/repository-physical-normalization/project_brief.md`
- `docs/capabilities/repository-physical-normalization/context_refs.md`
- `specs/capabilities/repository-physical-normalization/spec-001-repository-physical-normalization.md`
- `specs/capabilities/repository-physical-normalization/arch-001-repository-physical-normalization.md`
- `docs/capabilities/repository-physical-normalization/sdd_readiness_assessment.md`
- `docs/capabilities/repository-physical-normalization/tasks.md`
- `docs/capabilities/index.md`
- `specs/capabilities/index.md`
- `.github/instructions/sdd.instructions.md`
- `.github/agents/qa-gate.agent.md`

Resultado:

- `SDD Full` verificado desde Project Brief.
- `SPEC-001` existe y paso QA T-007.
- Architecture documental fue autorizada por T-008.
- `ARCH-001` existe, esta trazada a `SPEC-001` y fue revisada por Reviewer Agent en T-011.
- Reference map, movement plan y rollback plan estan definidos como componentes futuros no ejecutables.
- No hay implementacion prematura.
- No se crean scripts, tools, workflows, runtime ni automatizaciones.
- No se mueve, copia, renombra, sustituye ni elimina ningun archivo.
- No se modifican baselines cerrados.

Condiciones:

1. Cualquier ejecucion fisica futura requiere decision humana explicita posterior a este gate.
2. Antes de ejecutar movimientos debe existir reference map completo, canonical route registry, movement plan detallado y rollback plan detallado.
3. `SDD Modes` debe permanecer read-only hasta que exista plan ejecutable aprobado, review y QA especificos.
4. Development permanece `NOT AUTHORIZED`.
5. Normalizacion fisica permanece `NOT AUTHORIZED`.

Siguiente paso valido:

```text
Human decision on whether to authorize a future governed execution-preparation phase.
```

Development permanece `NOT AUTHORIZED`. No se autoriza normalizacion fisica.